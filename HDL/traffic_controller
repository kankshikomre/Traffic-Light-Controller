module traffic_controller(clk, reset, north_dir, south_dir, east_dir, west_dir, enable_n, enable_s, enable_e, enable_w, count1, count2, count3, count4); //*?*
  input logic clk,reset;
  output logic[2:0]north_dir, south_dir, east_dir, west_dir;
  output logic enable_n,enable_s,enable_e,enable_w;
  typedef enum bit[1:0] {north, south, east, west} directions; // using enum to specify the states present in FSM
  output logic [4:0] count1,count2,count3,count4; // trackers which counts 15s for each signal to make them red after 15s
  directions traffic_dir;
  
  counter counter1(.clk(clk),.enable(enable_n),.dir(north_dir),.count(count1));// specifying the counters for each signal by giving the clks which has period of  1s
  counter counter2(.clk(clk),.enable(enable_s),.dir(south_dir),.count(count2));
  counter counter3(.clk(clk),.enable(enable_e),.dir(east_dir),.count(count3));
  counter counter4(.clk(clk),.enable(enable_w),.dir(west_dir),.count(count4));
  
  
  always@(posedge clk) begin
  if(reset) begin
  enable_n = 0;  // every signal is red in every dir when no counter is running
  enable_s = 0;
  enable_e = 0; 
  enable_w = 0;
  traffic_dir <= north; 
  end
  
  else // when reset low
  begin
  unique case(traffic_dir)
  north:begin
  if(count1 == 14)
    begin
    enable_n <= 0; // after the counter running upto 15s it will turn off
    enable_s <= 1; // next one will immediately turn on
    traffic_dir <= south; // mentioning the next traffic direction state it has to go and check the counter
    end 
  else
    begin
      enable_n <= 1; // to make it start after reset is getting down
    end
  end
  
  south:begin
  if(count2 == 14)
    begin
    enable_s <= 0;
    enable_e <= 1;
    traffic_dir <= east;
    end 
  end
  
  east:begin
  if(count3 == 14)
    begin
    enable_e <= 0;
    enable_w <= 1;
    traffic_dir <= west;
    end 
  end
  
  west:begin
  if(count4 == 14)
    begin
    enable_w <= 0;
    enable_n <= 1;
    traffic_dir <= north;
    end 
  end
  
  endcase
  
  end
  end  
  
endmodule

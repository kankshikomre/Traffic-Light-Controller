module traffic_controller_tb;
  logic clk, reset;
  logic [2:0]north_dir, south_dir, east_dir, west_dir;
  logic enable_n,enable_s,enable_e,enable_w;
  logic [4:0] count1,count2,count3,count4;
  traffic_controller traffic_controller_tb(.clk(clk),.reset(reset),.north_dir(north_dir),.south_dir(south_dir),.east_dir(east_dir),.west_dir(west_dir),.enable_n(enable_n),.enable_s(enable_s),.enable_e(enable_e),.enable_w(enable_w),.count1(count1),.count2(count2),.count3(count3),.count4(count4));
  
  initial begin
  clk = 1'b0;
  reset = 1'b1;
  #10;
  reset = 1'b0;
  end
  
  initial begin
  #3000 $finish;
  end
  
  always #5 clk = ~clk; // clk of 100Mhz frequency with 10ns timeperiod //*?*

endmodule

//////////////////////////////////////////////////////////////////////////////////
// FREQUENCY DIVIDER //
//////////////////////////////////////////////////////////////////////////////////


module frequency_div(clk, slowed_clk, reset);
  input logic clk,reset; // example a clk running at 100MHz 
  parameter frequency = 100000000;
  output logic slowed_clk; // clock with time period 1s so that we can measure everything in seconds
  logic [25:0]tracker; // counter to track, so half time period of slowed clk represent 0 and another half represent 1.
  
  always@(posedge clk)
    begin
    if(reset)
      begin
        tracker <= 0; // initializing the tracker
        slowed_clk <= 0; // initializing the slowed clk 
      end
    else
        begin
          tracker <= tracker + 1;
          if(tracker < frequency/2) // half of the cycle will be zero
            begin
              slowed_clk <= slowed_clk;
            end
          else
            begin
              tracker <= 0;
              slowed_clk <= ~slowed_clk; // half of the cycle will be one
            end
        end
    end 
      
endmodule

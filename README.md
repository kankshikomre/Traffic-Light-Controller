# Traffic-Light-Controller

Using System Verilog FSM Coding to design a traffic light controller and verifying the design with a test bench:
  1. The two input signals in this are clk and reset, and the three output signals are north_dir, south_dir, east_dir, and west_dir are of 3 bits bit-width.
  2. Design will enter the north state and begin producing output when the reset signal is low. Green light will be activated for 10 seconds, followed by Yellow light for 5 seconds.
  3. Design will begin with the north, move into the south, then east, and lastly into the west. By doing this, it will continue.
  4. In the output signal, the letters "001" stand for Green light, "010" for Yellow light, and "100" for Red light.
  5. A frequency divider module is designed for measuring time in seconds.
  6. enum, and unique_case or unique_if are used.

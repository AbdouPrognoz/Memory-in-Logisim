# Memory in Logisim

A Logisim implementation of a 4-bit memory circuit using D flip-flops, decoder, multiplexer, and splitter.

## Steps

- A matrix of D flip-flops is made, with dimensions **32×5**, meaning there are 32 rows and in each row there are 4 D flip-flops.
- A **5×32 decoder** is used, with a 5-bit input given to the decoder as the address to access the row.
- The decoder's 32 output lines are connected to the flip-flops in every row as the **enable** lines.
- A 4-bit input is taken and connected bitwise to flip-flops in every row. For example, the first bit of input connects to the input of every flip-flop in the first column.
- There is a **clock input** in the circuit.
- For output, a **32×5 multiplexer** is used.
- Each row's bits are combined using a **splitter** and connected to the multiplexer.
- The 5-bit input used for the decoder is also used for the selection lines of the multiplexer.
- Output is shown from the output of the multiplexer.
- A **reset button** is provided to reset all flip-flops in the circuit.

## Working Example

To store `0111` at the address `10110`:

1. Give `0111` to the data input.
2. Set `10110` as the address.
3. This input is provided to every flip-flop in every row.
4. The corresponding enable line (23rd row in this case) is activated via the decoder.
5. Upon clock pulse, `0111` is stored in the flip-flops of the 23rd row.
6. The address `10110` is also used as the selection input in the multiplexer, passing the output from the 23rd row to the output.
7. To read data from any row, provide the row's address to display stored data.
8. The reset button clears all flip-flops in the circuit.

## Inputs

- **4-bit input:** Data to store.
- **5-bit input:** Address for storing 4-bit data.

## Outputs

- **4-bit output:** Data from the row corresponding to the given address.

## Circuit File Format

The `.circ` extension is used by Logisim to store the circuits in XML format, similar to HTML.

Bitm.app
=========
The World's Best Image Editor.

- Run the program from Terminal with `ruby run.rb`.
- Press `?` to get help.

Commands
=========
Bitm.app accepts commands with all kinds of spacing and capitalization errors. Go (reasonably) wild.

- `I M N` - Create a new M x N image with all pixels coloured white (O).
- `C` - Clears the table, setting all pixels to white (O).
- `L X Y C` - Colours the pixel (X,Y) with colour C.
- `V X Y1 Y2 C` - Draw a vertical segment of colour C in column X between rows Y1 and Y2 (inclusive).
- `H X1 X2 Y C` - Draw a horizontal segment of colour C in row Y between columns X1 and X2 (inclusive).
- `F X Y C` - Fill the region R with the colour C. R is defined as: Pixel (X,Y) belongs to R. Any other pixel which is the same colour as (X,Y) and shares a common side with any pixel in R also belongs to this region.
- `R` – Rotate the table.
- `S` - Show the contents of the current image
- `X` - Terminate the session


Why Matrices, not Arrays?
=========
Matrices are part of `stdlib`, rather than `corelib`. So why the extra dependency?

- It seems more natural to use Matrices to represent 2-dimensional data rather than Arrays of Arrays.
- Matrices have a whole bunch of convenient methods, like `transpose()` for rotation, and more natural `each_with_index()` enumeration methods.
- Matrices are immutable, which means we have to use stuff like `.send(:[]=)` to change elements, but they might be more memory-efficient at large scales.

TODO
=========

- Fill command is sometimes buggy if fill is directed to start on the first row of `@state`.
- Rotate command fails with large matrices. This may be a ruby bug.
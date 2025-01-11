# Konva Floor Plan Demo

This project demonstrates a freehand drawing tool that converts sketches into rectilinear polygons (e.g., rectangles) using the Konva.js library. The shapes are smoothed, snapped to horizontal/vertical edges, and cleaned to ensure proper geometry. This tool is ideal for creating floor plans or similar visualizations.

## Features

1. **Freehand Drawing**:
   - Users can draw freely in the "Sketch Stage".
   - Edges automatically snap to horizontal or vertical lines upon release.

2. **No Extra Points**:
   - Rectangles have exactly four corners (anchors).
   - Duplicate or unnecessary points are removed.

3. **Plan Stage**:
   - Converts finalized shapes into editable rectilinear polygons.
   - Shapes are draggable, and each corner (vertex) is represented by an anchor.

4. **Simplification and Snapping**:
   - Uses the Simplify.js library to reduce jitter and clean up freehand lines.
   - Ensures all edges are horizontal or vertical.

5. **Dynamic Interaction**:
   - Users can move anchors to adjust the shape dynamically in the "Plan Stage".

## How It Works

### Sketch Stage
1. **Drawing**:
   - Click and drag to draw a freehand shape.
   - The shape is represented as a series of points.

2. **Simplification**:
   - The points are smoothed using Simplify.js to reduce jitter.

3. **Snapping**:
   - Each edge snaps to the nearest horizontal or vertical line.

4. **Cleanup**:
   - Collinear points are removed.
   - Any redundant last point (duplicating the first point) is removed.

5. **Preview**:
   - The closed polygon is displayed in the "Sketch Stage" for visualization.

### Plan Stage
1. **Scaling**:
   - The shape is scaled to fit within the Plan Stage dimensions.

2. **Anchors and Lines**:
   - Each vertex becomes an anchor (draggable point).
   - Each edge is represented as an independent line connecting two anchors.

3. **Dynamic Adjustment**:
   - Users can drag anchors to reshape the polygon dynamically.

## How to Use

1. **Run the Code**:
   - Save the provided HTML file and open it in a web browser.

2. **Sketch a Shape**:
   - Draw a freehand shape in the "Sketch Stage" using your mouse or touch input.

3. **View the Plan**:
   - The finalized shape will appear in the "Plan Stage" as a rectilinear polygon with draggable anchors.

4. **Edit the Shape**:
   - Drag the anchors in the "Plan Stage" to adjust the shape dynamically.

## Dependencies

- **[Konva.js](https://konvajs.org/)**: A 2D canvas library for building interactive graphics.
- **[Simplify.js](https://github.com/mourner/simplify-js)**: A library for simplifying 2D geometry.

## Code Overview

### Key Functions

- **`finalizeSketch`**:
  - Converts raw freehand points into a cleaned polygon.
  - Applies snapping, simplification, and removes collinear points.

- **`snapToHV`**:
  - Snaps edges to horizontal or vertical directions based on movement.

- **`removeCollinearPoints`**:
  - Removes redundant points along straight lines.

- **`moveToPlanStage`**:
  - Scales and converts the cleaned shape into a rectilinear polygon with draggable anchors.

- **`updateLine`**:
  - Updates the lines between anchors dynamically as they are moved.

## Example Use Case

1. Draw a freehand rectangle in the "Sketch Stage".
2. Watch the shape snap to horizontal/vertical lines and clean up unnecessary points.
3. View the scaled version in the "Plan Stage" with draggable corners.
4. Adjust the anchors to fine-tune the shape.

## Future Improvements

- Add support for snapping to diagonal or custom angles.
- Allow for user-defined grid snapping.
- Export finalized shapes as JSON or SVG.

## License

This project is free to use under the MIT License.


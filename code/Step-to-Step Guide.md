# Step-by-Step Guide: Building the Simple Drawing Application in MIT App Inventor

This guide provides instructions on how to construct the Simple Drawing Application based on the provided MIT App Inventor screenshots.

## Step 1: Project Setup

1.  Navigate to the MIT App Inventor website (appinventor.mit.edu) and log in.
2.  Click **Projects** > **Start new project**.
3.  Enter a project name (e.g., `SimpleDrawingApp`) and click **OK**.

## Step 2: Designing the User Interface (Designer View)

Switch to the **Designer** view (usually the default view when you start a new project).

1.  **Add Layout:**
    * From the **Palette** > **Layout**, drag a **`HorizontalArrangement`** onto the Viewer.
    * Select the `HorizontalArrangement` in the Components list.
    * In the **Properties** pane, set its **`Width`** to **`Fill parent`**.

2.  **Add Color Buttons:**
    * From the **Palette** > **User Interface**, drag three **`Button`** components into the `HorizontalArrangement`.
    * **Button 1 (Red):**
        * Select the first `Button`.
        * In Properties, set **`Text`** to `RED`.
        * Set **`BackgroundColor`** to `Red`.
        * *Optional but Recommended:* Rename the component to `ButtonRed` in the Components list.
    * **Button 2 (Blue):**
        * Select the second `Button`.
        * In Properties, set **`Text`** to `BLUE`.
        * Set **`BackgroundColor`** to `Blue`.
        * *Optional:* Rename to `ButtonBlue`.
    * **Button 3 (Green):**
        * Select the third `Button`.
        * In Properties, set **`Text`** to `GREEN`.
        * Set **`BackgroundColor`** to `Green`.
        * *Optional:* Rename to `ButtonGreen`.

3.  **Add Canvas:**
    * From the **Palette** > **Drawing and Animation**, drag a **`Canvas`** component below the `HorizontalArrangement`.
    * Select the `Canvas`.
    * In Properties, set **`Width`** to **`Fill parent`**.
    * Set **`Height`** to **`Fill parent`** (or adjust as needed for your layout).
    * *Optional:* Rename to `DrawingCanvas`.

4.  **Add Clear Button:**
    * From the **Palette** > **User Interface**, drag a **`Button`** component below the `Canvas`.
    * Select this button.
    * In Properties, set **`Text`** to `REMOVE COLOUR`.
    * Set **`Width`** to **`Fill parent`**.
    * *Optional:* Rename to `ButtonClear`.

Your Designer view layout should now resemble the screenshot provided.

## Step 3: Programming the App Logic (Blocks Editor)

Click the **Blocks** button in the top right corner to switch to the Blocks Editor.

1.  **Implement Color Selection:**
    * Click on `ButtonRed` (or your renamed button) in the Blocks pane on the left. Drag out the **`when ButtonRed.Click do`** block.
    * Click on `DrawingCanvas`. Find and drag the **`set DrawingCanvas.PaintColor to`** block and place it inside the `when ButtonRed.Click do` block.
    * Click on **Built-in** > **Colors**. Drag the **`red`** color block and snap it into the `set DrawingCanvas.PaintColor` block.

    * Repeat these steps for `ButtonBlue` and `ButtonGreen`, using the corresponding `blue` and `green` color blocks.

2.  **Implement Clear Button:**
    * Click on `ButtonClear`. Drag out the **`when ButtonClear.Click do`** block.
    * Click on `DrawingCanvas`. Find and drag the **`call DrawingCanvas.Clear`** block and place it inside the `when ButtonClear.Click do` block.

3.  **Implement Drawing on Canvas (Touch):**
    * Click on `DrawingCanvas`. Drag out the **`when DrawingCanvas.Touched x y touchedAnySprite do`** block.
    * Inside this block, click on `DrawingCanvas` again. Find and drag the **`call DrawingCanvas.DrawCircle center x center y radius 5 fill true`** block.
    * Hover over the `x` variable in the `Touched` block header, select **`get x`**, and snap it into the `center x` socket.
    * Hover over the `y` variable, select **`get y`**, and snap it into the `center y` socket. (The radius is set to 5, and fill is true for a solid dot).

4.  **Implement Drawing on Canvas (Drag):**
    * Click on `DrawingCanvas`. Drag out the **`when DrawingCanvas.Dragged startX startY prevX prevY currentX currentY draggedAnySprite do`** block.
    * Inside this block, click on `DrawingCanvas` again. Find and drag the **`call DrawingCanvas.DrawLine x1 y1 x2 y2`** block.
    * Hover over the `prevX` variable, select **`get prevX`**, and snap it into the `x1` socket.
    * Hover over the `prevY` variable, select **`get prevY`**, and snap it into the `y1` socket.
    * Hover over the `currentX` variable, select **`get currentX`**, and snap it into the `x2` socket.
    * Hover over the `currentY` variable, select **`get currentY`**, and snap it into the `y2` socket.

Your Blocks workspace should now contain blocks similar to the screenshot provided, connected together as described above.

## Step 4: Testing the Application

1.  In the App Inventor web interface, click **Connect** in the top menu.
2.  Choose your preferred testing method:
    * **AI Companion:** Use the MIT AI2 Companion app on an Android device. Scan the QR code provided.
    * **Emulator:** Launch an Android emulator connected to App Inventor.
3.  Test the application on your device or emulator to ensure colors change and drawing works correctly with both touch and drag, and the clear button erases the canvas.

You have successfully built the Simple Drawing Application!

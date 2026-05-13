# CorelDRAW-SelectSmallObjects
A VBA macro for CorelDRAW (2020+) that automates the selection of vector objects based on user-defined dimensional thresholds.

# CorelDRAW Select Small Objects Macro

An automated cleanup tool for **CorelDRAW** that allows users to instantly select multiple vector objects based on specific width and height thresholds.

This macro is essential for designers working with complex vectorizations, high-texture brushes, or PowerTrace results that leave behind thousands of unwanted "specks."

## Features

* **Custom Thresholds:** Define maximum width and height in millimeters.
* **Logical Selection Rules:**
* **AND:** Selects objects only if *both* width and height are below the limit.
* **OR:** Selects objects if *either* the width or the height is below the limit.


* **High Performance:** Optimized to handle thousands of shapes simultaneously without crashing.
* **Instant Feedback:** Displays a dialogue box confirming the total number of objects selected.

## Installation

1. **Download** the `SelectSmallObject.gms` file from this repository.
2. **Navigate** to your CorelDRAW GMS folder. Typically:
`C:\Users\[YourUsername]\AppData\Roaming\Corel\CorelDRAW Graphics Suite 20xx\Draw\GMS`
*Note: If the folder doesn't exist, you can create it.*
3. **Paste** the `.gms` file into that folder.
4. **Restart** CorelDRAW.

## How to Use

1. Open your project in CorelDRAW.
2. Go to **Window > Dockers > Scripts** (or Macro Manager).
3. Expand `SelectSmallObject` and double-click `selectObjectsSmallerThanSize`.
4. Enter your desired dimensions (e.g., Width: $1.0$ mm, Height: $0.5$ mm).
5. Choose your **Selection Rule** (AND/OR).
6. Click **OK**. All matching objects on the active page will be highlighted.

## ⚙️ Technical Details

The macro iterates through the `ActivePage.Shapes` collection. It uses the following logic to determine selection:

* **AND Logic:** 
$$\text{Selection} = \{s \in \text{Shapes} \mid s.\text{Width} \le W_{\text{max}} \land s.\text{Height} \le H_{\text{max}}\}$$


* **OR Logic:** 
$$\text{Selection} = \{s \in \text{Shapes} \mid s.\text{Width} \le W_{\text{max}} \lor s.\text{Height} \le H_{\text{max}}\}$$



## Compatibility

* **CorelDRAW Graphics Suite** 2020, 2021, 2022, 2024, and 2026.
* Requires **VBA (Visual Basic for Applications)** to be enabled during CorelDRAW installation.

## License

This project is licensed under the MIT License - see the [LICENSE](https://www.google.com/search?q=LICENSE) file for details.

---

*Developed to make vector cleanup painless.*

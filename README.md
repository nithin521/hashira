# 🔢 Polynomial Solver Website

A **web-based mathematical tool** that solves polynomial equations from JSON data using **Shamir's Secret Sharing** principles.

## 🎯 What It Does

- Takes JSON input with points in different number bases (binary, hex, decimal, etc.)
- Converts all values to decimal automatically
- Uses linear algebra to find polynomial coefficients
- Extracts the "secret" (constant term) from the polynomial

## 💡 How It Works

1. **Input**: JSON with x,y coordinate pairs in various bases
2. **Conversion**: Transforms all bases (2-36) to decimal
3. **Math**: Builds and solves a matrix equation using the first k points
4. **Output**: Shows polynomial coefficients and verifies accuracy

## 🌟 Website Features

- **Modern UI**: Glassmorphism design with gradient backgrounds
- **Responsive Layout**: Works on desktop, tablet, and mobile
- **Real-time Processing**: Instant solving with loading animations
- **Error Handling**: Clear error messages for invalid input
- **Example Library**: 3 pre-loaded test cases (simple, complex, large numbers)
- **Interactive Buttons**: Bold, prominent example loading buttons
- **Detailed Analysis**: Step-by-step breakdown of the solving process
- **Visual Feedback**: Status messages, success/error indicators
- **High Precision Math**: Handles extremely large numbers accurately
- **Keyboard Shortcuts**: Ctrl+Enter to solve quickly

## 📥 Input Format

```json
{
 "keys": {
   "n": 10,        // Total points available
   "k": 7          // Points needed for polynomial
 },
 "1": {
   "base": "6",
   "value": "13444211440455345511"
 },
 "2": {
   "base": "15",   // Supports bases 2-36
   "value": "aed7015a346d635"  // Alphanumeric values
 },
 "3": {
   "base": "16",
   "value": "e1b5e05623d881f"
 }
 // ... more points
}

📤 Output Format

🔍 Analysis:
   Total points available (n): 10
   Points needed (k): 7
   Polynomial degree: 6

📊 Points used for calculation:
   Point 1: 13444211440455345511 (base 6) = 995085094601491
   Point 2: aed7015a346d635 (base 15) = 320923294898495940
   ...

🎯 Polynomial Coefficients (highest to lowest degree):
   [3, -2, 0, 5, 1, -7, 12345]

🔐 Secret (constant term): 12345

✅ Verification:
   P(1) = 995085094601491 ✓ (expected: 995085094601491)
   P(2) = 320923294898495940 ✓ (expected: 320923294898495940)
   ...

🎉 All points verified successfully!

P(x) = 3x⁶ - 2x⁵ + 5x³ + x² - 7x + 12345

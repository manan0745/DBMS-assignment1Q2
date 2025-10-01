This is created by Manan Khandelwal. 
Sap ID : 590014164 
Batch : 01

About this code:
This is a “Normalization Assistant” web tool.
It helps students or database learners practice Database Normalization (1NF → 2NF → 3NF → BCNF).
You enter Attributes (columns) and Functional Dependencies (FDs).
The tool automatically computes:
Attribute closures
Candidate keys
Prime attributes
Normal form steps (detects violations of 2NF, 3NF, BCNF)
Decompositions (relations in higher normal forms)
Lossless join check
Dependency preservation check
This is auto-generated JavaScript + HTML so users can visualize normalization concepts without needing SQL engines.
⚙️ How the code is structured
1. HTML Layout
<!doctype html> → modern HTML5.
<head>: sets meta tags, title, and CSS styling.
<body>: has a wrapper (div.wrap) containing:
Header → Title + short description.
Grid layout:
Main card (left side) → where user enters input and sees results.
Sidebar card (right side) → Quick help + explanation.
Footer → with usage tips.

2. CSS Styling
The styles make it look modern and dark-themed:
:root{--bg: ... } → CSS variables for background, colors, and accents.
Body → gradient dark background, light text.
Cards → glassmorphism effect (semi-transparent background, blur-like).
Buttons → styled with accent cyan color.
Output → boxes with dashed borders for results.
Responsive design with media queries (@media(max-width:1000px) → single column on small screens).

3. Inputs Section (Main card)
Input fields:
Attributes (comma separated: A,B,C,D).
Functional Dependencies (A -> B).
Buttons:
Compute Closures & Keys → finds closures + candidate keys.
Run Normalization Steps → shows 1NF, 2NF, 3NF, BCNF with explanations.
Reset → clears inputs & results.
Results display area:
Attribute closures
Candidate keys
Prime attributes
Steps display area:
Shows each NF step with analysis.

5. Quick Help (Sidebar card)
Explains input format.
Shows chips for concepts like “Lossless join” and “Dependency preservation”.

6. JavaScript Logic
The heart of the project – handles all database logic.
🔹 Utility functions:
parseAttrs() → parses attributes list (like A,B,C).
parseFDs() → parses functional dependencies (A,B -> C).
closure() → computes closure of an attribute set.
subsets() → generates subsets of attributes (used to check keys).
computeCandidateKeys() → finds all candidate keys.
implies() → checks if an FD is implied by a set.
projectFDs() → projects FDs on smaller relation.
isLossless() → checks if decomposition is lossless.
decomposeToBCNF() → recursive decomposition algorithm to BCNF.
🔹 Event Listeners:
Compute → runs closure + candidate key logic.
Normalize → step-by-step NF analysis:
1NF → assumes atomic.
2NF → detects partial dependencies.
3NF → detects transitive dependencies.
BCNF → decomposition algorithm.
Checks for lossless join and dependency preservation.
Clear → resets inputs/results.

Conclusion:
This is a self-contained web-based Normalization Assistant that applies DBMS normalization theory using JavaScript algorithms and interactive HTML UI. 
It was generated to make normalization easy, interactive, and visual for students.

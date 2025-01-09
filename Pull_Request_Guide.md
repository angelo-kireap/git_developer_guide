

# Guide on Pull Request

This document outlines the standard **Pull Request (PR) Format** and provides instructions for performing basic `commit` and `push` operations in Git. Following these guidelines will help maintain consistency and ensure smooth collaboration.

---

## Pull Request Format

When creating a Pull Request, use the following format to ensure clarity and proper documentation:

### **PR Title**  
- Keep it short and descriptive (e.g., "Fix issue with login form validation").

### **PR Description**  
Include the following sections in the description:

1. **Summary**  
   Briefly explain what the PR does and why it's necessary.

   Example:  
   > This PR fixes the login form validation issue by adding proper regex for email validation and handling edge cases.

2. **Changes Made**  
   List the key changes made in the PR.

   Example:  
   - Updated `validation.js` to fix email regex.  
   - Added test cases for invalid email formats.  

3. **Issue/Task Reference**  
   If the PR resolves an issue, include the reference (e.g., "Closes #123").

4. **Testing**  
   Describe how you tested the changes. Provide steps for reviewers to test locally.

   Example:  
   > - Open the login form and test various email formats.  
   > - Run `npm test` to verify automated tests pass.  

5. **Checklist**  
   Ensure these items are complete before requesting a review:  
   - [ ] Code is linted and formatted.  
   - [ ] Tests are updated (if applicable).  
   - [ ] Documentation is updated (if necessary).
   - 
5. **Images/Videos (Optional)**  
   Include images/videos  
---


## Sample PR

```bash
# PR Title

PR Description
[description ...                ]

   1. Summary
    This PR fixes the login form validation issue by adding proper regex for email validation and handling edge cases.

   2. Changes Made
        Updated validation.js to fix email regex.
        Added test cases for invalid email formats.
        Refactored login.js to improve error messaging.

   3. Issue/Task Reference
    Closes #456

   4. Testing
        Open the login form and test various email formats (valid and invalid).
        Run npm test to verify automated tests pass.
        Check error messages for empty and invalid inputs.

   5. Checklist

Code is linted and formatted.
Tests are updated (if applicable).

Documentation is updated (if necessary).

Images/Videos (Optional)

creenshot of error messages when invalid email is entered (attached).

```

## How to Commit and Push Changes

Follow these steps for basic commit and push operations in Git:

### 1. **Stage Your Changes**  
   Use `git add` to stage files for commit:  
   ```bash
   git add <file_name>  # Add a specific file
   git add .            # Add all changed files in the current directory
   ```

### 2. **Commit Your Changes**  
   Commit the staged changes with a descriptive message:  
   ```bash
   git commit -m "Add a descriptive message here"
   ```

   **Commit Message Guidelines**:  
   - Use the present tense (e.g., "Fix bug" instead of "Fixed bug").  
   - Be concise but informative.

   Example:  
   ```bash
   git commit -m "Fix email validation regex and add test cases"
   ```

### 3. **Push Your Changes**  
   Push your changes to the remote branch:  
   ```bash
   git push origin <branch_name>
   ```

   Replace `<branch_name>` with the name of your branch.

### 4. **Create a Pull Request**  
   - Navigate to your repository on GitHub.  
   - Click **"Compare & pull request"**.  
   - Fill out the PR form using the format described above.

---

## Example Workflow

```bash
# Clone the repository
git clone <repository-url>

# Create and switch to a new branch
git checkout -b feature/add-email-validation

# Make your changes, then stage them
git add .

# Commit your changes with a message
git commit -m "Add email validation and test cases"

# Push changes to the remote branch
git push origin feature/add-email-validation

# Create a pull request on GitHub
```

---

By following this guide, you ensure that your contributions are well-documented, easy to review, and maintainable. Happy coding! 🚀

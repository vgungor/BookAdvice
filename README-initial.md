This documentation provides an overview of the Book Advice/Recommendation App (BARA) based on the provided source code.

1. Business Requirements Document (BRD)
   Purpose :
   BARA is designed to provide a centralized, digital repository where users can view and suggest books for a collective library. It aims to streamline the recommendation process and maintain data integrity through administrative oversight.

Business Objectives

Knowledge Sharing: Enable a community of users to share book recommendations.
Data Accuracy: Prevent duplicate entries and ensure only authenticated users can contribute.
Administrative Control: Provide a mechanism for authorized personnel to curate the list by removing outdated or incorrect entries.
Accessibility: Ensure the platform is usable across desktop, tablet, and mobile devices.

2. Functional Requirements Document (FRD)
   User Roles
   Standard User: Can log in, view the book list, search for books, and suggest new titles.
   Admin User: Inherits all Standard User permissions plus the ability to delete any book from the system.

Key Functionalities
Authentication: Secure login system using email and password verification.
Book Viewing: _ Toggle between Card View (visual grid) and Table View (structured list).
Responsive design that adjusts columns based on screen size.
Search Engine: Real-time search by title or author (enabled when the library exceeds 10 entries).
Book Suggestion: _ Users can submit a Title and Author.
Duplicate Prevention: The system blocks submissions if a book with the same title and author already exists.
Admin Management: Delete functionality available in both Table and Card views for administrators.

3. Technical Design Document (TDD)
   System Architecture The application follows a monolithic architecture using PHP for server-side logic and JSON for data persistence.

Tech Stack
Backend: PHP 7.4+ (Session management, Filter validation).
Frontend: HTML5, CSS3, Bootstrap 4, FontAwesome 5.
Database: books.json (Flat-file JSON storage).
Security:
password_verify() for secure credential checking.
CSRF Token validation on all POST requests.
LOCK_EX during file writes to prevent data corruption.
Input sanitization via FILTER_SANITIZE_STRING and FILTER_SANITIZE_EMAIL.
Data Structure (books.json)

JSON
{
"id": "Integer (Primary Key)",
"title": "String",
"author": "String",
"advicer": "String (User Email)",
"genre": "String (Optional)",
"year": "Integer (Optional)"
}
Security Constraints

Session Fixation: session_regenerate_id(true) is called upon successful login.
Unauthorized Access: All core pages check for $\_SESSION['logged_in'] and redirect to index.php if false.

Admin Route Protection: The delete logic is wrapped in an $isAdmin conditional check.

4. User Documentation
   Getting Started

Login: Enter your registered email and password on the landing page.

Browsing: Use the "View" buttons at the top right of the list to switch between a grid of cards or a spreadsheet-style table.

Searching: If the library is large, a search bar will appear. Type a name or author to filter results instantly.

How to Suggest a Book

Navigate to the Suggest a Book section.

Enter the Book Name and Author.

Click Advise Book.

Note: If the book already exists, the system will alert you and block the submission to keep the library clean.

For Administrators

To remove a book, click the Delete button (red trash icon) next to any entry. You will be asked for confirmation before the book is permanently removed.

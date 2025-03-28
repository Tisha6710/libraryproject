# libraryproject
I have created this library project in python.
class Library:
    def __init__(self):
        self.books = [
            {"id": 101, "title": "The Lean Startup", "author": "Eric Ries", "status": "Available"},
            {"id": 102, "title": "Zero to One", "author": "Peter Thiel", "status": "Available"},
            {"id": 103, "title": "Atomic Habits", "author": "James Clear", "status": "Available"},
            {"id": 104, "title": "The 7 Habits of Highly Effective People", "author": "Stephen Covey", "status": "Available"},
            {"id": 105, "title": "The Art of War", "author": "Sun Tzu", "status": "Available"},
            {"id": 106, "title": "Python Crash Course", "author": "Eric Matthes", "status": "Available"},
            {"id": 107, "title": "Clean Code", "author": "Robert C. Martin", "status": "Available"},
            {"id": 108, "title": "The Pragmatic Programmer", "author": "Andrew Hunt", "status": "Available"},
            {"id": 109, "title": "Introduction to Algorithms", "author": "Thomas H. Cormen", "status": "Available"},
            {"id": 110, "title": "Design Patterns", "author": "Erich Gamma", "status": "Available"},
            {"id": 111, "title": "Sapiens", "author": "Yuval Noah Harari", "status": "Available"},
            {"id": 112, "title": "A Brief History of Time", "author": "Stephen Hawking", "status": "Available"},
            {"id": 113, "title": "The Selfish Gene", "author": "Richard Dawkins", "status": "Available"},
            {"id": 114, "title": "Cosmos", "author": "Carl Sagan", "status": "Available"},
            {"id": 115, "title": "Astrophysics for People in a Hurry", "author": "Neil deGrasse Tyson", "status": "Available"},
            {"id": 116, "title": "Rich Dad Poor Dad", "author": "Robert Kiyosaki", "status": "Available"},
            {"id": 117, "title": "The Intelligent Investor", "author": "Benjamin Graham", "status": "Available"},
            {"id": 118, "title": "Thinking, Fast and Slow", "author": "Daniel Kahneman", "status": "Available"},
            {"id": 119, "title": "The Power of Now", "author": "Eckhart Tolle", "status": "Available"},
            {"id": 120, "title": "Deep Work", "author": "Cal Newport", "status": "Available"}
        ]

    def view_books(self):
        print("\n📖 **List of Available Books:**")
        print("=" * 80)
        print("{:<6} {:<45} {:<25} {:<10}".format("ID", "Title", "Author", "Status"))
        print("=" * 80)
        for book in self.books:
            print("{:<6} {:<45} {:<25} {:<10}".format(book["id"], book["title"], book["author"], book["status"]))
        print("=" * 80)

    def issue_book(self):
        book_id = int(input("Enter Book ID to Issue: "))
        for book in self.books:
            if book["id"] == book_id:
                if book["status"] == "Available":
                    book["status"] = "Issued"
                    print(f"✅ '{book['title']}' has been issued!")
                    return
                else:
                    print("❌ Book is already issued!")
                    return
        print("❌ Book ID not found!")

    def return_book(self):
        book_id = int(input("Enter Book ID to Return: "))
        for book in self.books:
            if book["id"] == book_id:
                if book["status"] == "Issued":
                    book["status"] = "Available"
                    print(f"✅ '{book['title']}' has been returned!")
                    return
                else:
                    print("❌ This book was not issued.")
                    return
        print("❌ Book ID not found!")

def main():
    library = Library()
    while True:
        print("\n📚 Library Management System")
        print("1️⃣ Issue a Book")
        print("2️⃣ Return a Book")
        print("3️⃣ View All Books")
        print("4️⃣ Exit")
        choice = input("Enter your choice: ")

        if choice == "1":
            library.issue_book()
        elif choice == "2":
            library.return_book()
        elif choice == "3":
            library.view_books()
        elif choice == "4":
            print("\n📕 Exiting... Thank you!")
            break
        else:
            print("❌ Invalid choice! Please try again.")

if __name__ == "__main__":
    main()


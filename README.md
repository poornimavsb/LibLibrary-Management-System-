class Library:
    def __init__(self):
        self.books = ["1984", "To Kill a Mockingbird", "The Great Gatsby", "Harry Potter"]
        self.borrowed_books = {}

    def display_books(self):
        print("\n📚 Available Books:")
        for book in self.books:
            print(f"- {book}")

    def add_book(self, book_name):
        self.books.append(book_name)
        print(f"✅ Book '{book_name}' added to the library.")

    def borrow_book(self, book_name, user):
        if book_name in self.books:
            self.books.remove(book_name)
            self.borrowed_books[book_name] = user
            print(f"📖 '{book_name}' has been borrowed by {user}.")
        else:
            print(f"❌ Book '{book_name}' is not available.")

    def return_book(self, book_name):
        if book_name in self.borrowed_books:
            self.books.append(book_name)
            user = self.borrowed_books.pop(book_name)
            print(f"🔁 '{book_name}' returned by {user}.")
        else:
            print(f"❌ Book '{book_name}' was not borrowed.")

# --- Menu-Driven Program ---

library = Library()

while True:
    print("\n--- Library Menu ---")
    print("1. Display Books")
    print("2. Add Book")
    print("3. Borrow Book")
    print("4. Return Book")
    print("5. Exit")

    choice = input("Enter your choice (1-5): ")

    if choice == '1':
        library.display_books()
    elif choice == '2':
        book = input("Enter the name of the book to add: ")
        library.add_book(book)
    elif choice == '3':
        book = input("Enter the name of the book to borrow: ")
        user = input("Enter your name: ")
        library.borrow_book(book, user)
    elif choice == '4':
        book = input("Enter the name of the book to return: ")
        library.return_book(book)
    elif choice == '5':
        print("👋 Exiting Library System. Goodbye!")
        break
    else:
        print("❗ Invalid choice. Please select a number from 1 to 5.")# LibLibrary-Management-System-

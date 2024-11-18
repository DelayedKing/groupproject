import pickle

def save_books(book_list):
    with open("books.pickle", "wb") as file:
        pickle.dump(book_list, file)

def load_books():
    try:
        with open("books.pickle", "rb") as file:
            return pickle.load(file)
    except FileNotFoundError:
        return []

def add_book(book_list):
    title = input("Enter book title: ")
    author = input("Enter author name: ")
    year = input("Enter publication year: ")
    book = {"title": title, "author": author, "year": year}
    book_list.append(book)
    save_books(book_list)
    print(f"Book '{title}' added!")

def list_books(book_list):
    if not book_list:
        print("No books in the library.")
    else:
        for book in book_list:
            print(f"{book['title']} by {book['author']} ({book['year']})")

def search_books(book_list):
    query = input("Enter search term (title or author): ").lower()
    results = [book for book in book_list if query in book["title"].lower() or query in book["author"].lower()]
    if results:
        for book in results:
            print(f"{book['title']} by {book['author']} ({book['year']})")
    else:
        print("No matching books found.")

def main():
    book_list = load_books()

    while True:
        print("\nOptions: 1) Add Book  2) List Books  3) Search Books  4) Quit")
        choice = input("Choose an option: ")

        if choice == "1":
            add_book(book_list)

        elif choice == "2":
            list_books(book_list)

        elif choice == "3":
            search_books(book_list)

        elif choice == "4":
            print("Goodbye!")
            break

        else:
            print("Invalid option. Please try again.")

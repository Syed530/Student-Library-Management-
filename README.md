# Student-Library-Management-


class Library:
    
    def __init__(self, listofbooks):
        self.books= listofbooks
    def displayAvailableBooks(self):
        print("Books present in the library are: ")
        for book in self.books:
            print("\t*" + book)
    def borrowBook(self, bookName):
        if bookName in self.books:
            print(f"You have issued {bookName}. Use it properly and return it within 30 days.")
            self.books.remove(bookName)
            return True
        else:
            print("Sorry this book is either not available or has been already issued to someone else. Please wait until the book is returned")
            return False


    def returnBook(self, bookName):
        self.books.append(bookName)
        print("Thanks for returning/adding this book! I hope you enjoyed reading it.")
class Student:
    def requestBook(self):
        self.book= input("Enter the name of the book: ")
        return self.book
    def returnBook(self):
        self.book= input("Enter the book you want to return: ")
        return self.book

      
if __name__ == "__main__":
    centrallibrary= Library(["Algorithms", "Django", "clrs", "Python", "Python notes"])
    student= Student()
    # centrallibrary.displayAvailableBooks()
while True:
    Welcome= '''====Welcome to the central library===
    Please choose an option:
    1. List all the books
    2. request the books
    3. return the books
    4. exit the library
    '''
    print(Welcome)
    a= int(input("Enter a choice"))
    if a== 1:
        centrallibrary.displayAvailableBooks()
    elif a== 2:
        centrallibrary.borrowBook(student.requestBook())
    elif a== 3:
        centrallibrary.returnBook(student.returnBook())
    elif a== 4:
        print("Thanks for choosing central library")
        exit()
    else:
        print("Invalid choice")
    
    
    

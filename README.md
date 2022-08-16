class Library:
    def __init__(self,listofBooks):
        self.books = listofBooks

    def displaybooksname(self):
        print('***************Books present in library***********')
        for book in self.books:
            print(book)

    def borrowBook(self,bookName):
        if bookName in self.books:
            self.books.remove(bookName)
            return False
        else:
            print('THIS BOOK IS NOT AVAILABLE')
            return False



    def returnb(self,bookName):
        if bookName not in self.books:
            self.books.append(bookName)
            self.books[2]=self.books[-1]
            self.books.pop()
            return False



class Student:
    def requestBook(self):
        self.book=input('Enter the name of the book you want to borrow')
        return self.book
    def returnthebook(self):
        x=input('enter the name of the book  you want to return')
        print(x)
        return x


if __name__=="__main__":
    centralLibrary = Library(['ENGLISH', 'HINDI','MATHS','SCIENCE','GK','SST'])
    STUDENT = Student()

    while(True):
         welcomeMSG = '''================***********WELCOME TO THE LIBRAY************===========
          **PLEASE SELECT AN OPTION**
          1.LIST OF THE BOOKS
          2.REQUEST A BOOK
          3.ADD/RETURN A BOOK
          4.EXIT'''
         print(welcomeMSG)

         x=int(input('Enter your choice'))
         if x==1:
             centralLibrary.displaybooksname()

         elif x==2:
             centralLibrary.borrowBook(STUDENT.requestBook())
         elif x==3:
             centralLibrary.returnb(STUDENT.returnthebook())
         elif x==4:
             print('THANKYOU FOR VISITING')
         else:
             print('invalid choice')

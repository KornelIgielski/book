# book
package com.company;

public class BookReader {
    private String surname;
    private Book book1, book2;

    public BookReader(String surname, Book book1, Book book2) {
        surname = surname;
        this.book1 = book1 = null;
        this.book2 = book2 = null;

    }
    BookReader(String surname){
        this.surname=surname;
        this.book1=null;
        this.book2=null;
    }
    public void borrowBook(Book book){
        if(!book.isBorrowed){

            if(this.book1 == null){
                this.book1= book;
                book.isBorrowed=true;
            } else if(this.book2==null){
                this.book2= book;
                book.isBorrowed=true;
            }
        }
    }
    public void returnBook(Book book){
        if(book.isBorrowed==true){

            if(this.book1 == book){
                this.book1 = null;
                book.isBorrowed=false;
            } else if(this.book2==book){
                this.book2 = null;
                book.isBorrowed=false;
            }
        }
    }

    public String toString(){
        String result = "Nazwisko: " + this.surname;
        if(this.book1 !=null || this.book2 !=null) {

            result += "\nWypożyczone książki: ";
            if (this.book1 != null) {
                result += "\n" + this.book1;
            }
            if (this.book2 != null) {
                result += "\n" + this.book2;
            }
        }else{
            result+= "\nBrak wypożyczeń";
        }
            return result;
        }



}

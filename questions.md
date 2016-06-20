1. Think about arrays
- What are some of the methods (non-iterator methods) that you know?

  -count, first, last, sort, flatten, push, pop, unshift, shift

- When are they used?

  -first and last to get an example from the array 
  -flatten to remove complexity of nesting
  -discover an array's size/how many elements you're working with
  -push, pop, unshift, shift --> alter the contents of an array 

2. Now list iterator methods for arrays
- There are four main ones that we have discussed

  -each, map/collect, find/detect, select

- When do you use each one

  -each: for its side effects 
  -map: alter the composition of the collection
  -find: return the first element for which the code in the code block is true
  -select: return an array of elements for which the code in the code block is true

3. Now onto objects
1. Why do we even have objects?  Why not just use hashes?
  
  -for objects, you can customize methods 

2. What is the difference between using a getter method, and just referencing the instance variable?

  - you can't reference an instance variable outside the scope of a class, 
    so you'd only be able to reference it within the object

3. Should a method that finds the correct user by name (eg. find_by_name?) be a class method or instance method?  Why?

  -it should be a class method because it is cycling through objects (users)

4. How does initialize work in an object?

  -it is automatically called whenever you want to create a new object(ie when you 
  use the .new method)

5. What two methods will attr_accessor :name write?
Write them out please...
  def name=
    @name = name
  end

  def name
    @name
  end  

4. Object Relations
Consider books, authors and genres.
1. Draw out the relations between the objects.  Assume a book can only have one genre.     

    authors have many books and genres
    genres have many books
    books belong to authors and genres 

2. Which object is going act as my join - and thus store the data?

  book will be your join. the full list of books contains all the authors and 
  all the genres. 

3. Ok, now write out the three classes and fill in the belongs to relations.

class Book
attr_accessor :title, :author, :genre
@@all=[]
def initialize(title, author, genre)
@title = title 
@author = author 
@genre = genre
self.all
@@all
end
end

class Author

attr_accessor :name

def initialize(name)
@name = name
end
}

end

class Genre 
attr_accessor :genre 
def initialize(name)
@name = name
end
end

4. Now write the method that will give me a list of books written by an author.

books

self.find_by_author(author_name)
self.all.select{|book| book.author == author_name}
end


5. Now write a method that will give a list of all of the genre's of an author.

in authors... 

def find_genres
books.all.map{|book| 
if book.author == self.name
book.genre
end
}
end
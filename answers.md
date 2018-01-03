# Part 1
___
1.
  * Film
    * id(integer)
    * name(string)
    * year(integer)
  * Film_viewing
    * id(integer)
    * film_id(integer)(foreign key)
    * viewer_id(integer)(foreign key)
    * date(string)
  * Viewer
    * id(integer)
    * name(string)
    * age(integer)
2.
  * Worker
    * id(integer)
    * name(string)
    * wage(float)
  * Worker_shift
    * id(integer)
    * worker_id(integer)(foreign key)
    * shift_id(integer)(foreign key)
  * Shift
    * id(integer)
    * day(string)
    * time(string)
3.
  * Chapter
    * id(integer)
    * title(string)
    * book_id(integer)(foreign key)
  * Author
    * id(integer)
    * name(string)
  * Authored_books
    * author_id(integer)(foreign key)
    * book_id(integer)(foreign key)
    * publisher(string)
  * Book
    * id(integer)
    * title(string)
    * year(integer)
  * Books_read
    * reader_id(integer)(foreign key)
    * book_id(integer)(foreign key)
    * date(string)
  * Reader
    * id(integer)
    * name(string)
    * age(integer)

# Part 2

1. Comic, issue, artist, writer

Comic (one) - (many) issues
Comics (many) - (many) artists
Comics (many) - (many) writers

  * Comic
    * id(integer)
    * name(string)
  * Comic_credits
    * comic_id(integer)(foreign key)
    * artist_id(integer)(foreign key)
    * writer_id(integer)(foreign key)
  * Artist
    * id(integer)
    * name(string)
  * Writer
    * id(integer)
    * name(string)
  * Issue
    * id(integer)
    * name(string)
    * comic_id(integer)(foreign key)

2. Instrument, song, setlist, tour_date

Tour_dates (many) - (many) songs
Song (many) - (many) Instruments
Song (one) - (many) Setlist

  * Instrument
    * id(integer)
    * name(string)
  * Instruments_for_songs
    * id(integer)
    * instrument_id(integer)(foreign key)
    * song_id(integer)(foreign key)
  * Song
    * id(integer)
    * name(string)
  * Songs_for_tour
    * id(integer)
    * tour_id(integer)(foreign key)
    * song_id(integer)(foreign key)
  * Tour_date
    * id(integer)
    * name(string)
    * date(string)
  * Setlist
    * id(integer)
    * name(string)
    * song_id(integer)(foreign key)

3. gallery, exhibit, artwork, artist, curator

Gallery (one) - (many) exhibits
Exhibit (one) - (many) artworks
Artist (one) - (many) artworks
Artwork (many) - (many) curators

  * Gallery
    * id(integer)
    * name(string)
  * Exhibit
    * id(integer)
    * name(string)
    * gallery_id(integer)(foreign key)
  * Artwork
    * id(integer)
    * name(string)
    * exhibit_id(integer)(foreign key)
    * artist_id(integer)(foreign key)
  * Curation
    * id(integer)
    * artwork_id(integer)(foreign key)
    * curator_id(integer)(foreign key)
    * curation(text)
    * date(string)
  * Curator
    * id(integer)
    * name(string)
  * Artist
    * id(integer)
    * name(string)

4. Music piece, sheet music, instrument

Music_piece (one) - (many) sheet_music
Music_piece (many) - (many) instruments
Sheet music (one) - (one) instrument

  * Music_piece
    * id(integer)
    * name(string)
  * Sheet_music
    * id(integer)
    * name(string)
    * music_id(integer)(foreign key)
    * instrument_id(integer)(foreign key)
  * Instrument
    * id(integer)
    * name(string)

# Part 3

1. user, restaurant, dish, order

Restaurant (one) - (many) dishes
Restaurant (one) - (many) orders
Order (many) - (many) dishes
User (one) - (many) orders


  * User
    * id(integer)
    * name(string)
  * Restaurant
    * id(integer)
    * name(string)
  * Dish
    * id(integer)
    * name(string)
    * restaurant_id(integer)(foreign key)
  * Dishes_in_order
    * id(integer)
    * dish_id(integer)(foreign key)
    * order_id(integer)(foreign key)
  * Order
    * id(integer)
    * name(string)
    * user_id(integer)(foreign key)
    * restaurant_id(integer)(foreign key)

2. Airline, flight, passenger, crew

Airline (one) - (many) flights
Airline (one) - (many) crew
Flight (many) - (many) passengers
Flight (many) - (many) crew

  * Airline
    * id(integer)
    * name(string)
  * Crew
    * id(integer)
    * name(string)
    * airline_id(integer)(foreign key)
  * Passenger
    * id(integer)
    * name(string)
  * Flight_passenger_manifest
    * id(integer)
    * passenger_id(integer)(foreign key)
    * flight_id(integer)(foreign key)
  * Flight_crew_manifest
    * id(integer)
    * crew_id(integer)(foreign key)
    * flight_id(integer)(foreign key)
  * Flight
    * id(integer)
    * name(string)
    * airline_id(integer)(foreign key)
    * from_destination(string)
    * to_destination(string)
    * departure_time(string)

3. artist, track, user

Artist (one) - (many) tracks
User (many) - (many) artists
Artist (one) - (many) tracks

  * Artist
    * id(integer)
    * name(string)
  * Subscription
    * id(integer)
    * user_id(integer)(foreign key)
    * artist_id(integer)(foreign key)
  * User
    * id(integer)
    * name(string)
  * Track
    * id(integer)
    * name(string)
    * artist_id(integer)(foreign key)

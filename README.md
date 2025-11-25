# bus-ticket-system1
sequenceDiagram
    actor Passenger
    participant UI as User Interface
    participant System
    participant DB as Database

    Passenger ->> UI: Search for buses
    UI ->> System: Request bus list
    System ->> DB: Query available buses
    DB -->> System: Return results
    System -->> UI: Show bus list

    Passenger ->> UI: Select bus & seat
    UI ->> System: Request seat availability
    System ->> DB: Check seat status
    DB -->> System: Seat available
    System -->> UI: Seat confirmed

    Passenger ->> UI: Enter passenger details
    UI ->> System: Submit booking
    System ->> DB: Save booking, update seat
    DB -->> System: Booking saved

    System -->> UI: Generate digital ticket
    UI -->> Passenger: Show ticket

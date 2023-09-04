```python
'''
Week six: Project One
Project 1: Air traffic control simulation 
Problem: Imagine you're an air traffic controller during 
a busy day at the airport. Due to an emergency, some 
flights need to make an emergency landing. Design a 
system that prioritizes these emergency landings over 
regular scheduled flights. Develop a program that 
takes flight details, including emergency status, and 
manages the landing queue efficiently. 

'''
```


```python
from collections import deque

class Flight:
    def __init__(self, flight_number, emergency=False):
        self.flight_number = flight_number
        self.emergency = emergency

class AirTrafficControl:
    def __init__(self):
        self.emergency_queue = deque()
        self.scheduled_queue = deque()

    def add_flight(self, flight):
        if flight.emergency:
            self.emergency_queue.append(flight)
        else:
            self.scheduled_queue.append(flight)

    def process_flights(self):
        print("Processing flights:")
        while self.emergency_queue:
            emergency_flight = self.emergency_queue.popleft()
            print(f"Emergency landing: Flight {emergency_flight.flight_number}")
        while self.scheduled_queue:
            scheduled_flight = self.scheduled_queue.popleft()
            print(f"Scheduled landing: Flight {scheduled_flight.flight_number}")

def main():
    atc = AirTrafficControl()

    atc.add_flight(Flight("ABC123"))
    atc.add_flight(Flight("XYZ789", emergency=True))
    atc.add_flight(Flight("DEF456"))
    atc.add_flight(Flight("GHI987", emergency=True))

    atc.process_flights()

if __name__ == "__main__":
    main()
```

    Processing flights:
    Emergency landing: Flight XYZ789
    Emergency landing: Flight GHI987
    Scheduled landing: Flight ABC123
    Scheduled landing: Flight DEF456
    


```python

```


```python
'''
Project Two: File Handling
'''

class WordCounter:
    def __init__(self, filename):
        self.filename = filename
        self.word_count = {}

    def process_file(self):
        with open(self.filename, 'r') as file:
            content = file.read()
            words = content.split()
            for word in words:
                word = word.strip('.,!?()[]{}"\'')
                word = word.lower()
                if word:
                    if word in self.word_count:
                        self.word_count[word] += 1
                    else:
                        self.word_count[word] = 1

    def display_word_frequency(self):
        print("Word frequency in the file:")
        for word, count in self.word_count.items():
            print(f"{word}: {count}")

def main():
    filename = "C:/Users/ONYEKA INNOCENT/Desktop/demofile2.txt"  # Replace with the actual filename
    counter = WordCounter(filename)
    counter.process_file()
    counter.display_word_frequency()

if __name__ == "__main__":
    main()
```

    Word frequency in the file:
    i: 2
    am: 2
    learning: 2
    python: 1
    for: 1
    data: 1
    science: 1
    at: 1
    ingryd: 1
    academy: 1
    the: 2
    journey: 1
    has: 1
    been: 1
    a: 1
    fascinating: 1
    one: 2
    but: 1
    we: 1
    will: 1
    get: 1
    through: 2
    it: 1
    amen: 1
    that: 1
    knows: 1
    better: 1
    


```python

```


```python

```

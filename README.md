# Wikipedia Search Engine

This project is a simple GUI-based Wikipedia search engine built using Python's Tkinter library. The application allows users to enter a search query and retrieves a summary from Wikipedia.

## Features

- **Graphical User Interface (GUI)**: Easy-to-use interface built with Tkinter.
- **Wikipedia Integration**: Fetches and displays summaries from Wikipedia based on user input.
- **Scrollable Text Area**: Displays the fetched Wikipedia summary in a scrollable text area.

## Requirements

- Python 3.x
- `tkinter` library (usually included with standard Python installations)
- `wikipedia` library

## Installation

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/LunarHalf/search-engine.git
    cd search-engine
    

2. **Install Required Libraries**:
    ```bash
    pip install wikipedia
    ```

## Usage

1. **Run the Script**:
    ```bash
    python index.py
    ```

2. **Use the Application**:
    - Enter a search term in the entry box.
    - Click the "search" button.
    - The application will display the summary of the search term from Wikipedia in the text area below.

## Code Explanation

- **Imports**:
    ```python
    from tkinter import *
    import wikipedia
    ```

- **Function**:
    ```python
    def get_data():
        entry_value = entry.get()
        answer.delete(1.0, END)
        try:
            answer_value = wikipedia.summary(entry_value)
            answer.insert(INSERT, answer_value)
        except:
            answer.insert(INSERT, "ERROR! Invalid input or poor internet connection")
    ```

- **Main GUI Setup**:
    ```python
    win = Tk()
    win.title("Search Engine")
    
    topframe = Frame(win)
    entry = Entry(topframe)
    entry.pack()
    button = Button(topframe, text="search", command=get_data)
    button.pack()
    topframe.pack(side=TOP)

    bottomframe = Frame(win)
    scroll = Scrollbar(bottomframe)
    scroll.pack(side=RIGHT, fill=Y)
    answer = Text(bottomframe, width=200, height=80, yscrollcommand=scroll.set, wrap=WORD)
    scroll.config(command=answer.yview)
    answer.pack()
    bottomframe.pack()

    win.mainloop()
    ```

## Contributing

1. **Fork the Repository**:
    - Create a new branch for your feature or bug fix.
    - Commit your changes.
    - Push your branch and create a pull request.

2. **Open Issues**: If you find any bugs or have feature requests, please open an issue in the repository.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

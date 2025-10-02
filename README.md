---

# WikiLite: A Minimalist Wikipedia Reader

WikiLite is a single-file, client-side web application designed to provide a fast, focused, and low-bandwidth way to read Wikipedia articles. It supports features like language selection, a toggleable image display, and a unique **Summary Mode** that loads articles section-by-section using an accordion interface.

## 🚀 Features

* **Single File:** Everything—HTML, CSS, and JavaScript—is contained in one file, making deployment and sharing extremely simple.
* **Minimal Bandwidth:** Designed to reduce unnecessary data transfer, perfect for slower connections.
* **Language Selector:** Easily search and read articles from **10 popular language** versions of Wikipedia.
* **Summary Mode (Accordion):** Loads the article's lead section first, then allows users to load specific subsequent sections **on demand** by clicking the section title.
* **Image Toggle:** Quickly disable or enable images to save data and speed up rendering.
* **Internal Navigation:** Clicking internal Wikipedia links within a loaded article will open the new article within the modal, keeping the user in the app.
* **Scroll-to-Top Button:** A floating button appears in the article view for easy navigation back to the top of long articles.

## 🛠️ Setup and Usage

WikiLite is a pure client-side application and requires **no backend server** or complex setup.

### 1. Installation

1.  **Copy the code:** Take the complete HTML code provided for the project.
2.  **Save the file:** Save the code into a file named `index.html`.

### 2. Running the App

Simply **double-click** the `index.html` file in your file explorer. It will open directly in your default web browser (Chrome, Firefox, Edge, etc.).

### 3. Usage Guide

1.  **Search:** Enter a term into the search box.
2.  **Select Language:** Use the dropdown to choose the language of the Wikipedia site you want to search.
3.  **Settings:**
    * **Summary Mode (Default ON):** When checked, the article loads as collapsible sections. When unchecked, the full article HTML is loaded immediately (like a standard browser view).
    * **Show Images (Default ON):** Uncheck this to suppress all images within the article modal.
4.  **View Article:** Click on any search result to open the modal reader.
5.  **Navigate Sections (Summary Mode):** Click the section titles (e.g., "History," "Etymology") to fetch and display the content for that specific section.

## ⚙️ Technical Details

This project uses standard web technologies and relies entirely on the **Wikipedia API (MediaWiki API)** to fetch structured search results and parsed article content (HTML).

### API Endpoints Used:

* **Search:** `action=query&list=search`
* **Article Content:** `action=parse`
    * This is called with `section=0` to get the lead section, `prop=sections` to get the table of contents, and `section=N` to fetch specific sections on demand.

### Code Structure Highlights

* **Code Compression:** The HTML, CSS, and JavaScript have been heavily minified to reduce file size, optimizing the initial load time for slow internet connections.
* **JavaScript Efficiency:** Uses modern `async/await` for API calls and employs **event delegation** for efficient event handling on dynamically added elements (search results, sections, and internal links).
* **The Accordion Logic:** The `fetchSectionContent` function handles the core logic for the accordion, preventing redundant API calls for already loaded sections.

---

## 🤝 Contributing

While this project is intended to be a compact, self-contained utility, feel free to fork the repository if you wish to expand its features (e.g., adding more language options, implementing a dark mode, or improving the Wikipedia HTML cleanup).

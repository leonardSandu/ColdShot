# Cold Shot - Coffee & Craft Newsletter

This project is a dynamic, single-page web application designed to display a monthly newsletter. It's built with vanilla JavaScript and loads all its content from local JSON files, making it easy to update with new issues without touching the core HTML or JavaScript code.

## ✨ Features

* **Dynamic Content Loading**: All newsletter content (articles, images, links, etc.) is fetched from JSON files, keeping content separate from presentation.
* **Monthly Archive System**: The application automatically populates a dropdown menu with all available past newsletter issues, allowing users to navigate between them. The latest issue is loaded by default.
* **Modular Sections**: The page is broken down into distinct, reusable sections, including:
    * Featured Project
    * Master Speaks (Quote of the month)
    * Changing Timezones (Partner growth timeline)
    * Coffee Masters Highlights
    * Matcha Zone
    * Editor & Champion's Word
    * Knowledge Bites & Spread Kindness messages
    * Upcoming Certifications
* **Responsive Design**: The layout is fully responsive and adapts to devices of all sizes, from mobile phones to desktop monitors.
* **Centralized Configuration**: Key paths and settings are stored in a `CONFIG` object in the JavaScript, making it easy to manage the file structure.
* **Template Mode**: A built-in template view serves as a placeholder and guide for what content is needed for a new month.

## 📂 Project Structure

Here is the file structure the project relies on to dynamically load content.

* `index.html`
* **`allround-assets/`**
    * **`pictures/`**
        * `editor.png`
        * `champion.png`
        * `hero-background.svg`
    * `certifications-incoming.json`
    * `links.json`
* **`monthly-instances/`**
    * `months.json`
    * **`08.2025/`** (Example folder for a monthly issue)
        * **`activities/`**
            * **`featured/`**
                * `text.json`
                * `picture.png`
                * `project.pdf`
            * **`project-1/`** to **`project-6/`** (Each with `text.json`, `picture.png`, etc.)
        * **`changing-timezones/`**
            * `text.json`
            * `master-1-then.png`
            * `master-1-now.png`
            * `master-2-then.png`
            * `master-2-now.png`
        * **`master-speaks/`**
            * `text.json`
            * `master.png`
        * **`matcha-zone/`**
            * `text.json`
            * `picture.png`
            * `project.pdf`
        * `champion.json`
        * `editor.json`
        * `knowledge-bites.json`
        * `monthly-challange.json`
        * `spread-kindness.json`
## 🚀 How to Add a New Monthly Issue

To add a new newsletter for a new month, follow these steps:

1.  **Create a New Month Folder**: In the `monthly-instances/` directory, create a new folder using the `MM.YYYY` format (e.g., `09.2025`).

2.  **Add Content Files**: Copy the structure from a previous month (or the `template/` folder) into your new `MM.YYYY` folder. Populate the new folders with the content for the new month:
    * Update all `text.json` files with new titles, descriptions, names, and messages.
    * Replace `.png` image files with the new pictures for that month.
    * Add any relevant `.pdf` files for projects.
    * Update the root-level JSON files like `editor.json`, `champion.json`, `knowledge-bites.json`, etc.

3.  **Update `months.json`**: Open the `monthly-instances/months.json` file and add the name of your new folder to the list. The application will automatically sort it to appear as the latest issue.

    ```json
    {
      "months": [
        "08.2025",
        "09.2025"
      ]
    }
    ```

4.  **(Optional) Update Certifications**: If there are new certifications for the upcoming period, add them to the `allround-assets/certifications-incoming.json` file. The application will automatically filter and display only the ones relevant to the selected month.

## 🛠️ Local Development

To run this project locally, you can simply open the `index.html` file in a web browser.

However, due to modern browser security policies regarding `fetch()` for local files, it is **highly recommended** to use a local web server. An easy way to do this is with the "Live Server" extension in Visual Studio Code. This will prevent potential CORS errors and ensure the application behaves as it would on a live web server.

## 💻 Technologies Used

* **HTML5**
* **CSS3**: Custom properties (variables), Flexbox, Grid, and media queries for responsive design.
* **Vanilla JavaScript (ES6+)**: No frameworks. Uses modern features like `async/await` and the `fetch` API.
* **Font Awesome**: For icons used throughout the application.

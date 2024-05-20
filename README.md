## Overview

Overview
Summarized Review Chrome Extension is a tool designed to provide users with summarized reviews of products they are browsing online. Instead of sifting through numerous user reviews, this extension analyzes and presents a concise summary highlighting the key positive and negative points, allowing users to make informed decisions quickly.

##
## Features

Features
- **Real-time Review Summarization**: Fetches and summarizes reviews from live web pages.
- **User-Friendly Interface**: Simple and intuitive UI for ease of use.
- **Keyword-based Filtering**: Summarizes reviews based on user-defined keywords.
- **Positive and Negative Review Segregation**: Provides separate summaries for positive and negative reviews.
- **Notification Alerts**: Alerts users with summarized data through notifications.

##
## Installation Instructions

Installation Instructions

### Backend Setup
1. **Clone the repository**:
   ```bash
   git clone https://github.com/Capstone-Review-Summarization/ChromeExtension.git
   cd ChromeExtension/Summarized Review Extension - Server
   ```

2. **Set up a virtual environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate # On Windows use `venv\Scripts\activate`
   ```

3. **Install the requirements**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the Django server**:
   ```bash
   python manage.py migrate
   python manage.py runserver
   ```

### Frontend Setup
1. **Load the Extension**:
   - Open Chrome and navigate to `chrome://extensions/`.
   - Enable "Developer mode" using the toggle switch.
   - Click on "Load unpacked" and select the `Summarized Review Extension - Frontend` directory.

##
## Usage Examples

Usage Examples

1. **Activate the Extension**:
   - Open a product page on any e-commerce website.
   - Click on the Summarized Review Extension icon in the Chrome toolbar.
   - Click the "Get Summary" button to fetch and display summarized reviews.

2. **Keyword-based Summarization**:
   ```javascript
   $('#keywordsubmit').click(function(){
       chrome.runtime.sendMessage(
           'get_summarised_reviews',
           function(response) {
               let result = response.farewell;
               $('#positive_reviews').text(result.positive_review[0]);
               $('#negative_reviews').text(result.negative_review[0]);
               console.log(result);
           }
       );
   });
   ```

##
## Code Summary

Code Summary

### Backend (Django Server)

- **manage.py**: Entry point for the Django application, used for various administrative tasks.
- **extension/settings.py**: Contains all the configuration settings for the Django project.
- **extension/urls.py**: URL routing configuration for the project.
- **extension/wsgi.py** & **extension/asgi.py**: Configuration for WSGI and ASGI applications respectively.
- **summarization/models.py**: Defines the data models for the summarization application.
- **summarization/views.py**: Handles HTTP requests, processes data and returns JSON responses.
- **summarization/scrapper.py**: Contains logic for scraping review data from web pages.
- **summarization/apps.py**: Configuration for the Django application.
- **summarization/admin.py**, **summarization/tests.py**: For admin configuration and unit testing respectively.

### Frontend (Chrome Extension)

- **background.js**: Handles background tasks and manages communication with the server.
- **popup.js**: Manages events and actions in the extension's popup UI.
- **jquery-3.1.0.min.js**: jQuery library for ease of DOM manipulation and Ajax calls.

##
## License

License
This project is licensed under the MIT License. See the LICENSE file for more details.

```

Feel free to reach out if you have any questions or need further assistance!
```
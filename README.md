# Citation Processor

A web application that transforms Word documents with incomplete or improperly formatted endnotes into professionally formatted citations.

## Features

- **Smart Citation Lookup**: Automatically finds missing bibliographic data using Open Library API
- **Multiple Citation Styles**: Chicago, MLA, APA, and Bluebook
- **Incipit Format**: Optional scholarly incipit note format
- **Publisher Database**: 300+ publishers with automatic place inference
- **Web-Based**: No software installation required

## How It Works

1. **Upload** your Word document (.docx) with endnotes
2. **Select** your preferred citation style
3. **Choose** traditional or incipit format
4. **Download** your formatted document

The app will:
- Parse existing endnotes to extract author, title, publisher, etc.
- Look up missing data from Open Library
- Format citations according to your chosen style
- Return a clean, properly formatted document

## Deployment to Render

### One-Click Deploy

1. Push this repository to GitHub
2. Go to [Render](https://render.com)
3. Click "New +" → "Web Service"
4. Connect your GitHub repository
5. Render will automatically detect the `render.yaml` configuration
6. Click "Create Web Service"

### Manual Deploy

1. Create a new Web Service on Render
2. Connect your repository
3. Configure:
   - **Environment**: Python 3
   - **Build Command**: `pip install -r requirements.txt`
   - **Start Command**: `gunicorn app:app`
4. Deploy

## Local Development

```bash
# Install dependencies
pip install -r requirements.txt

# Run locally
python app.py

# Visit http://localhost:5000
```

## Project Structure

```
citation-processor/
├── app.py                 # Main Flask application
├── templates/
│   └── index.html        # Frontend interface
├── requirements.txt       # Python dependencies
├── render.yaml           # Render deployment config
└── README.md             # This file
```

## Technologies

- **Backend**: Flask (Python)
- **Frontend**: HTML, CSS, JavaScript
- **APIs**: Open Library for bibliographic data
- **Deployment**: Render
- **Document Processing**: python-docx, xml.dom.minidom

## Citation Styles Supported

- **Chicago Manual of Style**: Author, *Title* (Place: Publisher, Year).
- **MLA**: Author. *Title*. Publisher, Year.
- **APA**: Author (Year). *Title*. Place: Publisher.
- **Bluebook**: Author, TITLE (Publisher Year).

## Future Enhancements

- [ ] Manual citation editing interface
- [ ] Batch processing multiple documents
- [ ] Additional citation styles (Harvard, IEEE, etc.)
- [ ] Better parsing for complex citations
- [ ] Google Books API integration
- [ ] Citation export to BibTeX/EndNote

## Author

Eric Caplan

## License

MIT License

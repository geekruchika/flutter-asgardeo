# Asgardeo Flutter SDK Documentation

This directory contains the official documentation for the Asgardeo Flutter SDK.

## Documentation Structure

- **index.html** - Home page with overview and features
- **quickstart.html** - Step-by-step quick start guide
- **components.html** - Reference for all SDK components/widgets
- **api.html** - Complete API documentation
- **examples.html** - Real-world examples and use cases
- **styles.css** - Shared styles for all pages

## Viewing Locally

To view the documentation locally, simply open `index.html` in a web browser or use a local server:

```bash
# Using Python 3
python3 -m http.server 8000

# Using Node.js http-server
npx http-server

# Then open http://localhost:8000
```

## GitHub Pages Deployment

This documentation is designed to be deployed with GitHub Pages. To deploy:

1. Push the `docs/` folder to your GitHub repository
2. Go to repository Settings → Pages
3. Set Source to "Deploy from a branch"
4. Select branch: `main` and folder: `/docs`
5. Click Save

Your documentation will be available at: `https://yourusername.github.io/asgardeo-flutter/`

## Contributing

To contribute to the documentation:

1. Edit the HTML files directly
2. Test locally to ensure everything looks correct
3. Submit a pull request with your changes

## Structure Guidelines

- Keep navigation consistent across all pages
- Use the same CSS classes for consistent styling
- Add examples with complete, working code
- Include error handling in code examples
- Update the sidebar navigation when adding new sections

## License

Copyright © 2024 WSO2 LLC. All rights reserved.

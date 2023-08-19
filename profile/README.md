# Valesor Development

This repository contains the git modules needed to assemble the Valesor Development systems.

## Question: How do you add a script to the head element in a Hugo based site?

### Answer

In Hugo, a popular static site generator, you can add scripts to the `<head>` element of your HTML pages by modifying the template files. Here's how you can do it:

1. **Locate the Appropriate Template**: The main template file that controls the structure of your HTML pages is often named `baseof.html` or `layouts/_default/baseof.html`. This is the file you'll be working with to modify the `<head>` element.

2. **Edit the `<head>` Section**: Inside your `baseof.html` or equivalent template, locate the `<head>` section. It might look something like this:

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>{{ .Title }}</title>
        <!-- Add your scripts here -->
    </head>
    <body>
        <!-- Rest of your template content -->
    </body>
    </html>
    ```

3. **Add Your Script**: To add a script to the `<head>` element, you can use Hugo's template syntax. For instance, if you want to add an external JavaScript file, you can use the `{{ partial "js/script.html" }}` syntax. 

    Here's an example of how to include an external script:

    ```html
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>{{ .Title }}</title>
        {{ partial "js/script.html" }}
    </head>
    ```

4. **Create the Script Partial**: Create a partial HTML file for your script in the `layouts/partials` directory. For instance, if you named it `script.html`, it might look like this:

    ```html
    <script src="/js/your-script.js"></script>
    ```

    Make sure to adjust the path (`/js/your-script.js`) to match the actual location of your script file within your Hugo project.

5. **Place Your Script File**: Store your JavaScript file (in this example, `your-script.js`) in the appropriate directory within your project. If you used the path `/js/your-script.js`, create a directory named `js` at the root of your Hugo project and place the script file inside it.

6. **Build Your Site**: After making these changes, you'll need to build your Hugo site to see the updated changes. Run the following command in your terminal within your Hugo project directory:

    ```
    hugo
    ```

    This will generate the final HTML files with your added script in the `<head>` section.

Remember to ensure that your script URLs and file paths are correct and that you follow best practices for loading scripts to avoid any performance or compatibility issues.

## Question: What if I'm using a theme?

### Answer

If you're using a theme in Hugo, the process of adding a script to the `<head>` element may vary depending on how the theme is structured and how it allows you to customize your site. Here's a general approach you can follow:

1. **Locate Theme Templates**: Themes in Hugo often provide their own set of templates that control the layout and structure of your site. Look for the theme's template files that correspond to the `<head>` section of your HTML pages.

2. **Check Theme Documentation**: Before making changes, refer to the theme's documentation. Many themes offer customization options and guidelines on how to modify templates without breaking the theme's functionality.

3. **Create a Child Theme (Optional)**: To maintain your changes and updates to the original theme, consider creating a child theme. This involves copying the theme's templates into your own project's `layouts` directory and making modifications there. Child themes can help you avoid losing your changes when the original theme gets updated.

4. **Modify the `<head>` Section**: Locate the template file responsible for the `<head>` section (often `baseof.html` or similar) within the theme or your child theme's `layouts` directory. Add the necessary script code within the `<head>` section, using Hugo's template syntax as mentioned in the previous response.

5. **Customize the Script**: Depending on what you're trying to achieve, you might want to add an external script or inline JavaScript. Adjust the code accordingly, following the same principles outlined in the previous response.

6. **Test and Adjust**: After making your changes, test your site locally to ensure that the script is being included and working as expected. Check the browser's developer console for any errors related to the script.

7. **Build and Deploy**: If everything looks good, build your Hugo site and deploy it as you normally would. The changes you made to the `<head>` section should be included in the generated HTML files.

Remember that working with themes might involve some trial and error, especially if the theme's structure is complex. If the theme offers customization options through configuration files or partial templates, explore those possibilities before modifying the core theme templates. Always refer to the theme's documentation and try to adhere to best practices to avoid potential compatibility or maintenance issues.

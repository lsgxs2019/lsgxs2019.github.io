---
title: html文件中引用资源的路径
date: 2022-07-22 07:32:43
tags: 
  - html
  - 前端
categories: html
toc: true
cover: /2022/07/22/html文件中引用资源的路径/html-file-path.jpg
thumbnail: /2022/07/22/html文件中引用资源的路径/html-file-path.jpg
---



#### html文件中引用图片等文件的路径

## [File paths](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/Dealing_with_files#file_paths)

To make files talk to one another, you have to provide a file path between them — basically a route, so one file knows where another one is. To demonstrate this, we will insert a little bit of HTML into our `index.html` file, and make it display the image you chose in the article ["What will your website look like?"](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/What_will_your_website_look_like) Alternatively, you can choose an existing image at your disposal, on your computer or from the Web, and use it in the following steps:

<!--more-->

1. Copy the image you chose earlier into your `images` folder.

2. Open up your

    

   ```
   index.html
   ```

    

   file, and insert the following code into the file exactly as shown. Don't worry about what it all means for now — we'll look at the structures in more detail later in the series.

   ```
   <!DOCTYPE html>
   <html lang="en-US">
     <head>
       <meta charset="utf-8">
       <title>My test page</title>
     </head>
     <body>
       <img src="" alt="My test image">
     </body>
   </html>
   ```

   Copy to Clipboard

3. The line `<img src="" alt="My test image">` is the HTML code that inserts an image into the page. We need to tell the HTML where the image is. The image is inside the *images* directory, which is in the same directory as `index.html`. To walk down the file structure from `index.html` to our image, the file path we'd need is `images/your-image-filename`. For example, our image is called `firefox-icon.png`, so the file path is `images/firefox-icon.png`.

4. Insert the file path into your HTML code between the double quote marks of the `src=""` code.

5. Save your HTML file, then load it in your web browser (double-click the file). You should see your new webpage displaying your image!

![A screenshot of our basic website showing just the Firefox logo - a flaming fox wrapping the world](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/Dealing_with_files/website-screenshot.png)

Some general rules for file paths:

- To link to a target file in the same directory as the invoking HTML file, just use the filename, e.g. `my-image.jpg`.
  * 同目录直接书写文件名称
- To reference a file in a subdirectory, write the directory name in front of the path, plus a forward slash, e.g. `subdirectory/my-image.jpg`.
  * 资源在该html文件的子目录，书写子目录及文件路径
- To link to a target file in the directory **above** the invoking HTML file, write two dots. So for example, if `index.html` was inside a subfolder of `test-site` and `my-image.jpg` was inside `test-site`, you could reference `my-image.jpg` from `index.html` using `../my-image.jpg`.
  * 图片等资源在html文件的上一级目录，使用../filename.jpg
- You can combine these as much as you like, for example `../subdirectory/another-subdirectory/my-image.jpg`.
  * 可以使用../组合任意的子目录

For now, this is about all you need to know.

**Note:** The Windows file system tends to use backslashes, not forward slashes, e.g. `C:\Windows`. This doesn't matter in HTML — even if you are developing your website on Windows, you should still use forward slashes in your code.

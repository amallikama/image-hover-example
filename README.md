<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Hover Example</title>
</head>
<body>
    <div id="image" onmouseover="upDate(this)" onmouseout="upDateCancel()">
        <p id="imageText">Hover over an image below to display here</p>
        <img id="previewPic" src="default.jpg" alt="Default Image">
    </div>

    <img src="image1.jpg" alt="Image 1" onmouseover="upDate(this)" onmouseout="upDateCancel()">
    <img src="image2.jpg" alt="Image 2" onmouseover="upDate(this)" onmouseout="upDateCancel()">
    
    <script>
        function upDate(previewPic) {
            console.log(previewPic.src);
            document.getElementById('imageText').innerText = previewPic.alt;
            document.getElementById('previewPic').src = previewPic.src;
            document.getElementById('image').style.backgroundImage = `url('${previewPic.src}')`;
        }

        function upDateCancel() {
            document.getElementById('image').style.backgroundImage = 'url("")';
            document.getElementById('imageText').innerText = 'Hover over an image below to display here';
        }
    </script>
</body>
</html>

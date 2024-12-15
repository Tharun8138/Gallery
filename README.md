# Ex.08 Design of Interactive Image Gallery
# Date:15-12-2024
# AIM:
To design a web application for an inteactive image gallery with minimum five images.

# DESIGN STEPS:
## Step 1:
Clone the github repository and create Django admin interface.

## Step 2:
Change settings.py file to allow request from all hosts.

## Step 3:
Use CSS for positioning and styling.

## Step 4:
Write JavaScript program for implementing interactivity.

## Step 5:
Validate the HTML and CSS code.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Photo Gallery</title>
    <style>
        body {
            background-color: #7d7f7d;
            font-family: 'Open Sans', sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
        }

        .header {
            text-align: center;
            color: white;
            font-size: 24px;
            font-weight: bold;
            margin-bottom: 20px;
        }

        .gallery-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 15px;
            padding: 20px;
            max-width: 1200px;
            width: 100%;
            animation: fadeIn 1s ease-in-out;
        }

        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
        }

        .gallery-item img {
            width: 100%;
            height: auto;
            border-radius: 10px;
            transition: transform 0.3s ease, filter 0.3s ease;
        }

        .gallery-item img:hover {
            transform: scale(1.1);
            filter: brightness(0.8);
            cursor: pointer;
        }

        .caption {
            position: absolute;
            bottom: 8px;
            left: 8px;
            background-color: rgba(0, 0, 0, 0.7);
            color: white;
            padding: 4px 8px;
            border-radius: 4px;
            font-size: 12px;
            text-align: center;
            width: calc(100% - 16px);
        }

        .modal {
            display: none;
            position: fixed;
            z-index: 1;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            align-items: center;
            justify-content: center;
        }

        .modal-content {
            margin: auto;
            display: block;
            width: 80%;
            max-width: 600px;
            border-radius: 10px;
        }

        .close {
            position: absolute;
            top: 10px;
            right: 20px;
            color: white;
            font-size: 30px;
            cursor: pointer;
        }

        .modal-description {
            color: white;
            text-align: center;
            padding: 10px;
            font-size: 16px;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
    </style>
</head>
<body>

    <div class="header">Photo Gallery</div>

    <div class="gallery-container">
        <div class="gallery-item">
            <img src="pexels-photo-321570.jpeg" alt="Sri Lanka" data-description="Sri Lanka">
            <div class="caption">Sri Lanka</div>
        </div>
        <div class="gallery-item">
            <img src="photo-1609609830354-8f615d61b9c8.avif" alt="Isha Temple" data-description="Isha Temple">
            <div class="caption">Isha Temple</div>
        </div>
        <div class="gallery-item">
            <img src="premium_photo-1697730489433-4a5fe8a77f96.avif" alt="Mumbai" data-description="Mumbai">
            <div class="caption">Mumbai</div>
        </div>
        <div class="gallery-item">
            <img src="istockphoto-1073216888-612x612.jpg" alt="Bay Of Bengal" data-description="Bay Of Bengal">
            <div class="caption">Bay Of Bengal</div>
        </div>
        <div class="gallery-item">
            <img src="arch1.jpeg" alt="Australia" data-description="Australia">
            <div class="caption">Australia</div>
        </div>
    </div>

    <div class="modal" id="modal">
        <span class="close" id="close">&times;</span>
        <img class="modal-content" id="modal-img">
        <div class="modal-description" id="modal-description"></div>
    </div>

    <script>
        const images = document.querySelectorAll('.gallery-item img');
        const modal = document.getElementById('modal');
        const modalImg = document.getElementById('modal-img');
        const modalDescription = document.getElementById('modal-description');
        const closeBtn = document.getElementById('close');

        images.forEach((image) => {
            image.addEventListener('click', () => {
                modal.style.display = 'flex';
                modalImg.src = image.src;
                modalDescription.textContent = image.getAttribute('data-description');
            });
        });

        closeBtn.addEventListener('click', () => {
            modal.style.display = 'none';
        });
    </script>
</body>
</html>
```
# OUTPUT:
![Screenshot 2024-12-15 211310](https://github.com/user-attachments/assets/cc2bf4f0-9d53-454d-bf98-b90b5abf44a4)
![Screenshot 2024-12-15 211324](https://github.com/user-attachments/assets/1639afc1-8719-40a5-9f51-d3022d36a9a5)
![Screenshot 2024-12-15 211344](https://github.com/user-attachments/assets/77b176a2-8da2-4711-a0e4-00c29e2483f1)
![Screenshot 2024-12-15 211400](https://github.com/user-attachments/assets/28c7fbb2-cbb6-4144-ae5b-a95e1c8d9fde)
![Screenshot 2024-12-15 211416](https://github.com/user-attachments/assets/beae49d8-8dbb-4c48-9efa-6d6d77ce678f)
![Screenshot 2024-12-15 211431](https://github.com/user-attachments/assets/5b72c14d-06cc-4037-83bc-493614399651)

# RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.

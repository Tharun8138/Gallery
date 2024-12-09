# Ex.08 Design of Interactive Image Gallery
# Date:09-12-2024
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
    <title>Image Gallery</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        header {
            background-color: #333;
            color: #fff;
            padding: 1rem 0;
            text-align: center;
        }

        h1 {
            margin: 0;
            font-size: 2.5rem;
        }

        .filters {
            text-align: center;
            margin: 1rem 0;
        }

        .filters button {
            background-color: #333;
            color: #fff;
            padding: 0.5rem 1rem;
            margin: 0 0.5rem;
            border: none;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .filters button:hover, .filters button.active {
            background-color: #555;
        }

        .gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            margin: 2rem;
        }

        .gallery-item {
            position: relative;
            margin: 10px;
            overflow: hidden;
            cursor: pointer;
        }

        .gallery-item img {
            width: 100%;
            height: auto;
            transition: transform 0.3s ease, filter 0.3s ease;
        }

        .gallery-item:hover img {
            transform: scale(1.1);
            filter: brightness(0.7);
        }

        .gallery-item .overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            background-color: rgba(0, 0, 0, 0.5);
            color: #fff;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .gallery-item:hover .overlay {
            opacity: 1;
        }

        .lightbox {
            display: none;
            position: fixed;
            z-index: 999;
            padding-top: 60px;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0,0,0,0.8);
        }

        .lightbox-content {
            margin: auto;
            display: block;
            max-width: 80%;
        }

        .close {
            position: absolute;
            top: 15px;
            right: 35px;
            color: #fff;
            font-size: 40px;
            font-weight: bold;
            cursor: pointer;
        }

        @media (max-width: 768px) {
            .gallery-item {
                width: 100%;
                max-width: 100%;
            }
        }

        @media (min-width: 769px) {
            .gallery-item {
                width: 30%;
                max-width: 30%;
            }
        }
    </style>
</head>
<body>
    <header>
        <h1>Image Gallery</h1>
    </header>
    <div class="filters">
        <button class="filter-btn active" data-filter="all">All</button>
        <button class="filter-btn" data-filter="nature">Nature</button>
        <button class="filter-btn" data-filter="architecture">Architecture</button>
        <button class="filter-btn" data-filter="people">People</button>
    </div>
    <section class="gallery">
        <div class="gallery-item" data-category="nature">
            <img width="200" height="200" src="nature1.jpeg">
            <div class="overlay">Nature</div>
        </div>
        <div class="gallery-item" data-category="architecture">
            <img width="200" height="200" src="arch1.jpeg">
            <div class="overlay">Architecture</div>
        </div>
        <div class="gallery-item" data-category="people">
            <img width="200" height="200" src="people.jpeg">
            <div class="overlay">People</div>
        </div>
        <div class="gallery-item" data-category="nature">
            <img width="200" height="200" src="pexels-photo-321570.jpeg">
            <div class="overlay">Nature</div>
        </div>
        <div class="gallery-item" data-category="architecture">
            <img width="200" height="200" src="arch2.jpeg">
            <div class="overlay">Architecture</div>
        </div>
        <div class="gallery-item" data-category="people">
            <img width="200" height="200" src="people4.jpeg">
            <div class="overlay">People</div>
        </div>
    </section>
    <div id="lightbox" class="lightbox">
        <span class="close">&times;</span>
        <img class="lightbox-content" id="lightbox-image">
    </div>
    <script>
        const lightbox = document.getElementById('lightbox');
        const lightboxImg = document.getElementById('lightbox-image');
        const close = document.getElementsByClassName('close')[0];

        document.querySelectorAll('.gallery-item img').forEach(img => {
            img.addEventListener('click', function(event) {
                event.preventDefault();
                lightbox.style.display = 'block';
                lightboxImg.src = this.src;
            });
        });

        close.onclick = function() {
            lightbox.style.display = 'none';
        };

        window.onclick = function(event) {
            if (event.target === lightbox) {
                lightbox.style.display = 'none';
            }
        };

        const filterBtns = document.querySelectorAll('.filter-btn');
        const galleryItems = document.querySelectorAll('.gallery-item');

        filterBtns.forEach(btn => {
            btn.addEventListener('click', () => {
                filterBtns.forEach(b => b.classList.remove('active'));
                btn.classList.add('active');

                const filter = btn.getAttribute('data-filter');

                galleryItems.forEach(item => {
                    if (filter === 'all' || item.getAttribute('data-category') === filter) {
                        item.style.display = 'block';
                    } else {
                        item.style.display = 'none';
                    }
                });
            });
        });
    </script>
</body>
</html>
```
# OUTPUT:
![Screenshot 2024-12-09 212600](https://github.com/user-attachments/assets/045e7804-534d-4e8f-9afd-59359a39c658)
![Screenshot 2024-12-09 212627](https://github.com/user-attachments/assets/a4b8119f-0041-43ec-b1fd-98ccf8102db9)
![Screenshot 2024-12-09 212638](https://github.com/user-attachments/assets/b11508b4-cbbd-4053-be22-c910302c8f62)
![Screenshot 2024-12-09 212655](https://github.com/user-attachments/assets/1110b32d-5808-40aa-9b8a-4160267b2e43)




# RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.

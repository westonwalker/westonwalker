---
title: 5 Design Tips to Make your Boring Bootstrap Sites Beautiful
description: Still using Bootstrap CSS? Here's 5 design tips to make your Bootstrap UI's beautiful.
publishDate: 2022-06-27
published: true
---

Bootstrap is an amazing CSS framework for those who struggle with design, css, or need to build something quickly.

But the Bootstrap components you copy and paste from the documentation have flaws.

These flaws are holding back your designs!

Here are 5 design tips to correct those flaws and improve Bootstrap.

## 1) Bring attention to alerts

Add dark borders and svg icons to draw user's attention.

![Bootstrap improve alert components](https://i.imgur.com/0BjmR4j.png)

```html
<div class="alert alert-primary rounded-0 border-0 border-start border-primary border-4" role="alert">
    <p class="fs-6 mb-0 d-flex align-items-center">
        <!-- https://heroicons.com/ light-bul-->
        <svg xmlns="http://www.w3.org/2000/svg" class="me-1" width="16" height="16" viewBox="0 0 20 20" fill="currentColor">
            <path d="M11 3a1 1 0 10-2 0v1a1 1 0 102 0V3zM15.657 5.757a1 1 0 00-1.414-1.414l-.707.707a1 1 0 001.414 1.414l.707-.707zM18 10a1 1 0 01-1 1h-1a1 1 0 110-2h1a1 1 0 011 1zM5.05 6.464A1 1 0 106.464 5.05l-.707-.707a1 1 0 00-1.414 1.414l.707.707zM5 10a1 1 0 01-1 1H3a1 1 0 110-2h1a1 1 0 011 1zM8 16v-1h4v1a2 2 0 11-4 0zM12 14c.015-.34.208-.646.477-.859a4 4 0 10-4.954 0c.27.213.462.519.476.859h4.002z" />
        </svg>
        <span>A simple primary alert—check it out!</span>
    </p>
</div>
```


## 2) Tables don't have to match your database

HTML tables don't have to be a copy of your database structure. Remove column names, id's, and combine fields when it makes sense.

![Bootstrap CSS tables](https://i.imgur.com/UJQKDRe.png)

```html
<div class="border-0 shadow bg-white rounded">
    <h3 class="fs-5 px-3 pt-3">Users</h3>
    <div class="px-2 pt-2">
        <table class="table table-borderless fs-6">
            <tbody>
                <tr>
                    <td>Mark Otto</td>
                    <td class="text-end text-muted">@mdo</td>
                </tr>
                <tr class="bg-light rounded-4">
                    <td>Jacob Thornton</td>
                    <td class="text-end text-muted">@fat</td>
                </tr>
                <tr>
                    <td>Larry the Bird</td>
                    <td class="text-end text-muted">@twitter</td>
                </tr>
            </tbody>
        </table>
    </div>
    <div class="p-3 bg-light rounded d-flex justify-content-end">
        <buttons class="btn btn-link text-secondary text-decoration-none">Cancel</buttons>
        <buttons class="btn btn-primary">View</buttons>
    </div>
</div>
```

## 3) Secondary buttons don't need a background color

Giving primary actions a background color and secondary actions no background color will establish a hierarchy of importance.

![Bootstrap secondary buttons](https://i.imgur.com/kL1eKFQ.png)

```html
<div class="card border-0 shadow p-2">
    <div class="card-body">
        <h5 class="card-title">Special offer</h5>
        <p class="card-text">Are you sure you want to cancel your subscription? We have a special offer if you want to stick around!</p>
        
        <buttons class="btn btn-primary">View Details</buttons>
        <buttons class="btn btn-link text-secondary text-decoration-none">Cancel</buttons>
    </div>
</div>
```

## 4) Stop labeling everything!

Devs love to label values. Stop it! Display information as if it were a sentence in a book, not a key value pair.

![Bootstrap - stop labeling values](https://i.imgur.com/W07HyDj.png)

```html
<div class="card border-0 shadow">
    <img src="..." class="card-img-top" alt="...">
    <div class="card-body">
        <h1 class="card-title fs-5">Rocky Mount, MI</h1>
        <h2 class="card-title fs-6 text-muted fw-light">100 miles away</h2>
        <p class="card-text fw-light"><span class="fw-bold">$150</span> night</p>
    </div>
</div>
```

## 5) Shadows > Borders

Card borders often feel clunky. Shadows emphasize elements and give the page depth, making the element feel closer to the user.

![Bootstrap use shadows](https://i.imgur.com/TOVExal.png)

```html
<div class="card border-0 shadow p-2">
    <div class="card-body">
        <h5 class="card-title fs-5">Collaborate</h5>
        <p class="card-text">
            Share your work with hundreds of like minded individuals around the world!
        </p>
    </div>
</div>
```


## More Bootstrap design tips??

If you enjoyed this, consider checking out my new project - [Better Bootstrap](https://better-bootstrap.com)

There you will find a free book containing more Bootstrap design tips like the ones in this article.

<better-bootstrap-tease></better-bootstrap-tease>




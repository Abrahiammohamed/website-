<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>

    <style>
:root {
    --main-color: #2196f3;
    --main-color-alt: #1787e0;
    --main-transition: 0.3s;
    --main-padding-top: 100px;
    --main-padding-bottom: 100px;
    --section-background: #ececec;
  }
  a {
    text-decoration: none;
  }
  ul {
    list-style: none;
    margin: 0;
    padding: 0;
  }
  .container {
    padding-left: 15px;
    padding-right: 15px;
    margin-left: auto;
    margin-right: auto;
  }
  /* Small */
  @media (min-width: 768px) {
    .container {
      width: 750px;
    }
  }
  /* Medium */
  @media (min-width: 992px) {
    .container {
      width: 970px;
    }
  }
  /* Large */
  @media (min-width: 1200px) {
    .container {
      width: 1170px;
    }
  }
  .main-title {
    text-transform: uppercase;
    margin: 0 auto 80px;
    border: 2px solid black;
    padding: 10px 20px;
    font-size: 30px;
    width: fit-content;
    position: relative;
    z-index: 1;
    transition: var(--main-transition);
  }
  .main-title::before,
  .main-title::after {
    content: "";
    width: 12px;
    height: 12px;
    background-color: var(--main-color);
    position: absolute;
    border-radius: 50%;
    top: 50%;
    transform: translateY(-50%);
  }

  .main-title::before {
    left: -30px;
  }
  .main-title::after {
    right: -30px;
  }
  .main-title:hover::before {
    z-index: -1;
    animation: left-move 0.5s linear forwards;
  }
  .main-title:hover::after {
    z-index: -1;
    animation: right-move 0.5s linear forwards;
  }
  .main-title:hover {
    color: white;
    border: 2px solid white;
    transition-delay: 0.5s;
  }
  .spikes {
    position: relative;
  }
  .spikes::after {
    content: "";
    position: absolute;
    right: 0;
    width: 100%;
    height: 30px;
    z-index: 1;
    background-image: linear-gradient(135deg, white 25%, transparent 25%),
      linear-gradient(225deg, white 25%, transparent 25%);
    background-size: 30px 30px;
  }
  .dots {
    background-image: url("../imgs/dots.png");
    height: 186px;
    width: 204px;
    background-repeat: no-repeat;
    position: absolute;
  }
  .dots-up {
    top: 200px;
    right: 0;
  }
  .dots-down {
    bottom: 200px;
    left: 0;
  }
  /* End Global Rules */
  /* Start Header */
  .header {
    background-color: white;
    position: relative;
    -webkit-box-shadow: 0 0 10px #ddd;
    -moz-box-shadow: 0 0 10px #ddd;
    box-shadow: 0 0 10px #ddd;
  }
  .header .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    position: relative;
  }
  .header .logo {
    color: var(--main-color);
    font-size: 26px;
    font-weight: bold;
    height: 72px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  @media (max-width: 767px) {
    .header .logo {
      width: 100%;
      height: 50px;
    }
  }
  .header .main-nav {
    display: flex;
  }
  @media (max-width: 767px) {
    .header .main-nav {
      margin: auto;
    }
  }
  .header .main-nav > li:hover .mega-menu {
    opacity: 1;
    z-index: 100;
    top: calc(100% + 1px);
  }
  .header .main-nav > li > a {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 72px;
    position: relative;
    color: black;
    padding: 0 30px;
    overflow: hidden;
    font-size: 18px;
    transition: var(--main-transition);
  }
  @media (max-width: 767px) {
    .header .main-nav > li > a {
      padding: 10px;
      font-size: 14px;
      height: 40px;
    }
  }
  .header .main-nav > li > a::before {
    content: "";
    position: absolute;
    width: 100%;
    height: 4px;
    background-color: var(--main-color);
    top: 0;
    left: -100%;
    transition: var(--main-transition);
  }
  .header .main-nav > li > a:hover {
    color: var(--main-color);
    background-color: #fafafa;
  }
  .header .main-nav > li > a:hover::before {
    left: 0;
  }
  .header .mega-menu {
    position: absolute;
    width: 100%;
    left: 0;
    padding: 30px;
    background-color: white;
    border-bottom: 3px solid var(--main-color);
    z-index: -1;
    display: flex;
    gap: 40px;
    top: calc(100% + 50px);
    opacity: 0;
    transition: top var(--main-transition), opacity var(--main-transition);
  }
  @media (max-width: 767px) {
    .header .mega-menu {
      flex-direction: column;
      gap: 0;
      padding: 5px;
    }
  }
  .header .mega-menu .image img {
    max-width: 100%;
  }
  @media (max-width: 991px) {
    .header .mega-menu .image {
      display: none;
    }
  }
  .header .mega-menu .links {
    min-width: 250px;
    flex: 1;
  }
  .header .mega-menu .links li {
    position: relative;
  }
  .header .mega-menu .links li:not(:last-child) {
    border-bottom: 1px solid #e9e6e6;
  }
  @media (max-width: 767px) {
    .header .mega-menu .links:first-of-type li:last-child {
      border-bottom: 1px solid #e9e6e6;
    }
  }
  .header .mega-menu .links li::before {
    content: "";
    position: absolute;
    left: 0;
    top: 0;
    width: 0;
    height: 100%;
    background-color: #fafafa;
    z-index: -1;
    transition: var(--main-transition);
  }
  .header .mega-menu .links li:hover::before {
    width: 100%;
  }
  .header .mega-menu .links li a {
    color: var(--main-color);
    padding: 15px;
    display: block;
    font-size: 18px;
    font-weight: bold;
  }
  .header .mega-menu .links li a i {
    margin-right: 10px;
  }
  /* End Header */
  /* Start Landing */
  .landing {
    position: relative;
  }
  .landing::before {
    content: "";
    position: absolute;
    left: 0;
    top: -40px;
    width: 100%;
    height: 100%;
    background-color: #ececec;
    z-index: -1;
    transform: skewY(-6deg);
    transform-origin: top left;
  }
  .landing .container {
    min-height: calc(100vh - 72px);
    display: flex;
    align-items: center;
    padding-bottom: 120px;
  }
  .landing .text {
    flex: 1;
  }
  @media (max-width: 991px) {
    .landing .text {
      text-align: center;
    }
  }
  .landing .text h1 {
    font-size: 40px;
    margin: 0;
    letter-spacing: -2px;
  }
  @media (max-width: 767px) {
    .landing .text h1 {
      font-size: 28px;
    }
  }
  .landing .text p {
    font-size: 23px;
    line-height: 1.7;
    margin: 5px 0 0;
    color: #666;
    max-width: 500px;
  }
  @media (max-width: 991px) {
    .landing .text p {
      margin: 10px auto;
    }
  }
  @media (max-width: 767px) {
    .landing .text p {
      font-size: 18px;
    }
  }
  .landing .image img {
    position: relative;
    width: 600px;
    animation: up-and-down 5s linear infinite;
  }
  @media (max-width: 991px) {
    .landing .image {
      display: none;
    }
  }
  .landing .go-down {
    color: var(--main-color);
    position: absolute;
    bottom: 30px;
    left: 50%;
    transform: translateX(-50%);
    transition: var(--main-transition);
  }
  .landing .go-down:hover {
    color: var(--main-color-alt);
  }
  .landing .go-down i {
    animation: bouncing 1.5s infinite;
  }
  /* End Landing */
  /* Start Articles */
  .articles {
    padding-top: var(--main-padding-top);
    padding-bottom: var(--main-padding-bottom);
    position: relative;
  }
  .articles .container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 40px;
  }
  .articles .box {
    box-shadow: 0 2px 15px rgb(0 0 0 / 10%);
    background-color: white;
    border-radius: 6px;
    overflow: hidden;
    transition: transform var(--main-transition), box-shadow var(--main-transition);
  }
  .articles .box:hover {
    transform: translateY(-10px);
    box-shadow: 0 2px 15px rgb(0 0 0 / 20%);
  }
  .articles .box img {
    width: 100%;
    max-width: 100%;
  }
  .articles .box .content {
    padding: 20px;
  }
  .articles .box .content h3 {
    margin: 0;
  }
  .articles .box .content p {
    margin: 10px 0 0;
    line-height: 1.5;
    color: #777;
  }
  .articles .box .info {
    padding: 20px;
    border-top: 1px solid #e6e6e7;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .articles .box .info a {
    color: var(--main-color);
    font-weight: bold;
  }
  .articles .box .info i {
    color: var(--main-color);
  }
  .articles .box:hover .info i {
    animation: moving-arrow 0.6s linear infinite;
  }
  /* End Articles */
  /* Start Gallery */
  .gallery {
    padding-top: var(--main-padding-top);
    padding-bottom: var(--main-padding-bottom);
    position: relative;
    background-color: var(--section-background);
  }
  .gallery .container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 40px;
  }
  .gallery .box {
    padding: 15px;
    background-color: white;
    box-shadow: 0px 12px 20px 0px rgb(0 0 0 / 13%), 0px 2px 4px 0px rgb(0 0 0 / 12%);
  }
  .gallery .box .image {
    position: relative;
    overflow: hidden;
  }
  .gallery .box .image::before {
    content: "";
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: rgb(255 255 255 / 20%);
    width: 0;
    height: 0;
    opacity: 0;
    z-index: 2;
  }
  .gallery .box .image:hover::before {
    animation: flashing 0.7s;
  }
  .gallery .box img {
    max-width: 100%;
    transition: var(--main-transition);
  }
  .gallery .box .image:hover img {
    transform: rotate(5deg) scale(1.1);
  }
  /* End Gallery */
  /* Start Features */
  .features {
    padding-top: var(--main-padding-top);
    padding-bottom: var(--main-padding-bottom);
    position: relative;
    background-color: white;
  }
  .features .container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 40px;
  }
  .features .box {
    text-align: center;
    border: 1px solid #ccc;
  }
  .features .box .img-holder {
    position: relative;
    overflow: hidden;
  }
  .features .box .img-holder::before {
    content: "";
    position: absolute;
    left: 0;
    top: -1px;
    width: 100%;
    height: 100%;
  }
  .features .box .img-holder::after {
    content: "";
    position: absolute;
    bottom: 0;
    right: 0;
    border-style: solid;
    border-width: 0px 0px 170px 500px;
    border-color: transparent transparent white transparent;
    transition: var(--main-transition);
  }
  .features .box .img-holder img {
    max-width: 100%;
  }
  .features .box:hover .img-holder::after {
    border-width: 170px 500px 170px 0;
  }
  .features .box h2 {
    position: relative;
    font-size: 40px;
    margin: auto;
    width: fit-content;
  }
  .features .box h2::after {
    content: "";
    position: absolute;
    bottom: -20px;
    left: 15px;
    height: 5px;
    width: calc(100% - 30px);
  }
  .features .box p {
    line-height: 2;
    font-size: 20px;
    margin: 30px 0;
    padding: 25px;
    color: #777;
  }
  .features .box a {
    display: block;
    border: 3px solid transparent;
    width: fit-content;
    margin: 0 auto 30px;
    font-weight: bold;
    font-size: 22px;
    padding: 10px 30px;
    border-radius: 6px;
    transition: var(--main-transition);
  }
  .features .quality .img-holder::before {
    background-color: rgb(244 64 54 / 60%);
  }
  .features .quality h2::after {
    background-color: #f44036;
  }
  .features .quality a {
    color: #f44036;
    border-color: #f44036;
    background: linear-gradient(to right, #f44036 50%, white 50%);
    background-size: 200% 100%;
    background-position: right bottom;
  }
  .features .time .img-holder::before {
    background-color: rgb(0 150 136 / 60%);
  }
  .features .time h2::after {
    background-color: #009688;
  }
  .features .time a {
    color: #009688;
    border-color: #009688;
    background: linear-gradient(to right, #009688 50%, white 50%);
    background-size: 200% 100%;
    background-position: right bottom;
  }
  .features .passion .img-holder::before {
    background-color: rgb(3 169 244 / 60%);
  }
  .features .passion h2::after {
    background-color: #03a9f4;
  }
  .features .passion a {
    color: #03a9f4;
    border-color: #03a9f4;
    background: linear-gradient(to right, #03a9f4 50%, white 50%);
    background-size: 200% 100%;
    background-position: right bottom;
  }
  .features .box:hover a {
    background-position: left bottom;
    color: white;
  }
  /* End Features */
  /* Start Testimonials */
  .testimonials {
    padding-top: var(--main-padding-top);
    padding-bottom: var(--main-padding-bottom);
    position: relative;
    background-color: var(--section-background);
  }
  .testimonials .container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 40px;
  }
  .testimonials .box {
    padding: 20px;
    background-color: white;
    box-shadow: 0 2px 4px rgb(0 0 0 / 7%);
    border-radius: 6px;
    position: relative;
  }
  .testimonials .box img {
    position: absolute;
    right: -10px;
    top: -50px;
    width: 100px;
    height: 100px;
    border-radius: 50%;
    border: 10px solid var(--section-background);
  }
  .testimonials .box h3 {
    margin: 0 0 10px;
  }
  .testimonials .box .title {
    color: #777;
    margin-bottom: 10px;
    display: block;
  }
  .testimonials .box .rate .filled {
    color: #ffc107;
  }
  .testimonials .box p {
    line-height: 1.5;
    color: #777;
    margin-top: 10px;
    margin-bottom: 0;
  }
  /* End Testimonials */
  /* Start Team */
  .team {
    padding-top: var(--main-padding-top);
    padding-bottom: var(--main-padding-bottom);
    position: relative;
  }
  .team .container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 30px;
  }
  .team .box {
    position: relative;
  }
  .team .box::before,
  .team .box::after {
    content: "";
    background-color: #f3f3f3;
    position: absolute;
    right: 0;
    top: 0;
    height: 100%;
    border-radius: 10px;
    transition: var(--main-transition);
  }
  .team .box::before {
    width: calc(100% - 60px);
    z-index: -2;
  }
  .team .box::after {
    z-index: -1;
    background-color: #e4e4e4;
    width: 0;
  }
  .team .box:hover::after {
    width: calc(100% - 60px);
  }
  .team .box .data {
    display: flex;
    align-items: center;
    padding-top: 60px;
  }
  .team .box .data img {
    width: calc(100% - 60px);
    transition: var(--main-transition);
    border-radius: 10px;
  }
  .team .box:hover img {
    filter: grayscale(100%);
  }
  .team .box .data .social {
    width: 60px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
  }
  .team .box .data .social a {
    width: 60px;
    height: 30px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .team .box .data .social a:hover i {
    color: var(--main-color);
  }
  .team .box .data .social i {
    color: #777;
    transition: var(--main-transition);
  }
  .team .box .info {
    padding-left: 80px;
  }
  .team .box .info h3 {
    margin-bottom: 0;
    color: var(--main-color);
    font-size: 22px;
    transition: var(--main-transition);
  }
  .team .box .info p {
    margin-top: 10px;
    margin-bottom: 25px;
  }
  .team .box:hover .info h3 {
    color: #777;
  }
  /* End Team */
  /* Start Services */
  .services {
    padding-top: var(--main-padding-top);
    padding-bottom: var(--main-padding-bottom);
    position: relative;
    background-color: var(--section-background);
  }
  .services .container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 40px;
  }
  .services .box {
    background-color: white;
    box-shadow: 0 12px 20px 0 rgb(0 0 0 / 13%), 0 2px 4px 0 rgb(0 0 0 / 12%);
    counter-increment: services;
    transition: var(--main-transition);
    position: relative;
  }
  .services .box::before {
    content: "";
    left: 50%;
    transform: translateX(-50%);
    height: 3px;
    top: -3px;
    background-color: var(--main-color);
    position: absolute;
    width: 0;
    transition: var(--main-transition);
  }
  .services .box:hover {
    transform: translateY(-10px);
  }
  .services .box:hover::before {
    width: 100%;
  }
  .services .box > i {
    margin: 30px auto 20px;
    display: block;
    text-align: center;
    color: #d5d5d5;
  }
  .services .box > h3 {
    text-align: center;
    margin: 20px 0 40px;
    font-size: 25px;
    color: var(--main-color);
  }
  .services .box .info {
    padding: 15px;
    position: relative;
    background-color: #f9f9f9;
    text-align: right;
  }
  .services .box .info::before {
    content: "0" counter(services);
    position: absolute;
    background-color: var(--main-color);
    color: white;
    left: 0;
    top: 0;
    height: 100%;
    width: 80px;
    font-size: 30px;
    font-weight: bold;
    display: flex;
    justify-content: center;
    align-items: center;
    padding-right: 15px;
  }

    </style>
</head>
<body>
    <div class="header" id="header">
      <div class="container">
        <a href="#" class="logo">HEMA</a>
        <ul class="main-nav">
          <li><a href="#articles">Articles</a></li>
          <li><a href="#gallery">Gallery</a></li>
          <li><a href="#features">Features</a></li>
          <li>
            <a href="#">Other Links</a>
            <!-- Start Megamenu -->
            <div class="mega-menu">
              <div class="image">
                <img src="c:\Users\PcDoctor\Desktop\New folder (2)\2.JPG" alt="" />
              </div>
              <ul class="links">
                <li>
                  <a href="#testimonials"><i class="far fa-comments fa-fw"></i> Testimonials</a>
                </li>
                <li>
                  <a href="#team"><i class="far fa-user fa-fw"></i> Team Members</a>
                </li>
                <li>
                  <a href="#services"><i class="far fa-building fa-fw"></i> Services</a>
                </li>
                <li>
                  <a href="#our-skills"><i class="far fa-check-circle fa-fw"></i> Our Skills</a>
                </li>
                <li>
                  <a href="#work-steps"><i class="far fa-clipboard fa-fw"></i> How It Works</a>
                </li>
              </ul>
              <ul class="links">
                <li>
                  <a href="#events"><i class="far fa-calendar-alt fa-fw"></i> Events</a>
                </li>
                <li>
                  <a href="#pricing"><i class="fas fa-server fa-fw"></i> Pricing Plans</a>
                </li>
                <li>
                    <a href="#video"><i class="far fa-play-circle fa-fw"></i> Top Videos</a>
                  </li>
                  <li>
                    <a href="#stats"><i class="far fa-chart-bar fa-fw"></i> Stats</a>
                  </li>
                  <li>
                    <a href="#discount"><i class="fas fa-percent fa-fw"></i> Request A Discount</a>
                  </li>
                </ul>
              </div>
              <!-- End Megamenu -->
            </li>
          </ul>
        </div>
      </div>
<!-- End Header -->
    <!-- Start Landing -->
    <div class="landing">
        <div class="container">
          <div class="text">
           <em> <h1>I am Abrahiam Mohamed</h1></em>
            <p>موقع تعليم البرمجه انشاء مواقع ويب
    <li>انشاء منصات تعليميه</li>   
                <li>انشاء Website </li>
                
            </p>
          </div>
          <div class="image">
            <img src="c:\Users\PcDoctor\Desktop\New folder (2)\2.JPG" alt="" />
          </div>
        </div>
        <a href="#articles" class="go-down">
          <i class="fas fa-angle-double-down fa-2x"></i>
        </a>
    </div>
    <!-- End Landing -->
    <!-- Start Articles -->
    <div class="articles" id="articles">
      <h2 class="main-title">Articles</h2>
      <div class="container">
        <div class="box">
          <img src="vcvb.jpg" alt="" />
          <div class="content">
            <h3>Test Title</h3>
            <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Reprehenderit</p>
          </div>
          <div class="info">
            <a href="">Read More</a>
            <i class="fas fa-long-arrow-alt-right"></i>
          </div>
        </div>

        <div class="box">
            <img src="c:\Users\PcDoctor\Desktop\New folder (2)\2.JPG" alt="" />
            <div class="content">
              <h3>Test Title</h3>
              <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Reprehenderit</p>
            </div>
            <div class="info">
              <a href="">Read More</a>
              <i class="fas fa-long-arrow-alt-right"></i>
            </div>
          </div>

          <div class="box">
            <img src="c:\Users\PcDoctor\Desktop\New folder (2)\2.JPG" alt="" />
            <div class="content">
              <h3>Test Title</h3>
              <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Reprehenderit</p>
            </div>
            <div class="info">
              <a href="">Read More</a>
              <i class="fas fa-long-arrow-alt-right"></i>
            </div>
          </div>

          <div class="box">
            <img src="c:\Users\PcDoctor\Desktop\New folder (2)\IMG_20240720_110815.jpg" alt="" />
            <div class="content">
              <h3>Test Title</h3>
              <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Reprehenderit</p>
            </div>
            <div class="info">
              <a href="">Read More</a>
              <i class="fas fa-long-arrow-alt-right"></i>
            </div>
          </div> <div class="box">
            <img src="c:\Users\PcDoctor\Desktop\New folder (2)\IMG_20240720_110815.jpg" alt="" />
            <div class="content">
              <h3>Test Title</h3>
              <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Reprehenderit</p>
            </div>
            <div class="info">
              <a href="">Read More</a>
              <i class="fas fa-long-arrow-alt-right"></i>
            </div>
          </div> <div class="box">
            <img src="c:\Users\PcDoctor\Desktop\New folder (2)\IMG_20240720_110815.jpg" alt="" />
            <div class="content">
              <h3>Test Title</h3>
              <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Reprehenderit</p>
            </div>
            <div class="info">
              <a href="">Read More</a>
              <i class="fas fa-long-arrow-alt-right"></i>
            </div>
          </div>










</body>
</html>

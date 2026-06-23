<!DOCTYPE html>
<html>
<head>
    <title>Navbar Layout</title>

    <style>
        body {
            margin: 0;
            font-family: Arial;
            background: lightcoral;
            text-align: center;
            opacity: 1;
            transition: opacity 0.5 ease;
        }
        
        body.fade-out {
      opacity: 0;
        }
    
        

        nav {
            display: flex;
            align-items: center;
            justify-content: space-between;
            background: white;
            padding: 15px 30px;
        }

        .left, .right {
            display: flex;
            gap: 15px;
        }

        .left a, .right a {
            text-decoration: none;
            color: black;
            font-weight: bold;
            transition: 0.2s;
        }

        .left a:hover, .right a:hover {
            color: blue;
            transform: scale(1.1);
        }

        .center {
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            font-weight: bold;
            font-size: 18px;
        }

        button {
            text-align: center;
            padding: 10px 5px;
            margin: 0 auto;
            background-color: blue;
            color: white;
            border: 2px solid black;
            transition: 0.3s;
        }

        button:hover {
            background-color: darkblue;
            transform: scale(1.1);
        }

        .section {
    opacity: 0;
    transform: translateY(40px);
    transition: all 0.8s ease;
}

.section.show {
    opacity: 1;
    transform: translateY(0);
}



    </style>
</head>

<body>

<nav>
    <!-- LEFT -->
    <div class="left">
        <a href="Home.html">Home</a>
        <a href="About.html">About</a>
        <a href="services.html">Services</a>
    </div>

    <!-- CENTER -->
    <div class="center">
       <h2> My Website </h2>
    </div>

    <!-- RIGHT -->
    <div class="right">
        <a href="register.html">Register</a>
        <a href="login.html">Login</a>
    </div>
</nav>



<h1> This is the main Page  </h1>


<p> <u>Hello guys, Welcome to my mini Website.. Actually I am Learning HTML and CSS right now. So i just make to test my skills.. <br>
      Hope you guys like it and I am just a Normal Boy who lives in Nepal and reads in Class 9 </p> </u>


<br>
<br>
<br>
<br>

<b> Made By AarbikSubedi </b>  <br>
<br>
<br>



<button> Explore More </button>


<script>
document.querySelectorAll("a").forEach(link => {
    link.addEventListener("click", function(e) {
        const href = this.getAttribute("href");

        if (href && !href.startsWith("#")) {
            e.preventDefault();

            document.body.classList.add("fade-out");

            setTimeout(() => {
                window.location.href = href;
            }, 400);
        }
    });
});
</script>


<script>
const sections = document.querySelectorAll(".section");

function revealOnScroll() {
    const triggerBottom = window.innerHeight * 0.85;

    sections.forEach(section => {
        const top = section.getBoundingClientRect().top;

        if (top < triggerBottom) {
            section.classList.add("show");
        }
    });
}

window.addEventListener("scroll", revealOnScroll);
window.addEventListener("load", revealOnScroll);
</script>


</body>
</html>

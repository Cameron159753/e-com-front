<template>
  <div class="middle">
<h1>About</h1>
<div class="container">
  <img src="https://i.postimg.cc/fTmnGPKP/d2f5c06a-629d-4f20-a092-9e56315a80b3.webp" alt="" style="width:100%;">
  <div class="text-block">
<div class="contentp">
<p></p>
<br>
<p>
</p>
  </div>
</div>
</div>
</div>
<div class="boxed">
   <h1>OUR CORE VALUES</h1>
<ul>
    <li style="--accent-color:#60c5a6">
        <div class="icon"><i class="fa-brands fa-codepen"></i></div>
        <div class="title">Be Adventurous, Creative, and Open-Minded</div>
    </li>
    <li style="--accent-color:#f20071">
        <div class="icon"><i class="fa-brands fa-html5"></i></div>
        <div class="title">Create Long-Term Relationships with Our Customers</div>
    </li>
    <li style="--accent-color:#FCBA35">
        <div class="icon"><i class="fa-brands fa-css3"></i></div>
        <div class="title">Pursue Growth and Learning</div>
    </li>
    <li style="--accent-color:#DAE438">
        <div class="icon"><i class="fa-brands fa-js"></i></div>
        <div class="title">Inspire Happiness and Positivity</div>
    </li>
    <li style="--accent-color:#994D7F">
        <div class="icon"><i class="fa-brands fa-github"></i></div>
        <div class="title">Make Sure Our Customers are Pleased</div>
    </li>
</ul> 
</div>
</template>

<script>
export default {

}
</script>

<style>

@import url("https://pro.fontawesome.com/releases/v6.0.0-beta1/css/all.css");
@import url("https://fonts.googleapis.com/css2?family=Jura:wght@500;600;900&display=swap");

.middle {
  padding-top: 80px;
}

p{
  font-size: 13px;
}
.contentp{
     position: absolute;
  bottom: 0;
  background: rgb(255, 255, 255); /* Fallback color */
  background: rgba(0, 0, 0, 0.5); /* Black background with 0.5 opacity */
  color: #f1f1f1;
  width: 99%;
  padding: 20px;
}

.container {
  position: relative;
  font-family: Arial;
}



@media only screen and (max-width: 990px){
    .text-effect{ font-size: 65px; }
}
@media only screen and (max-width: 767px){
    .text-effect{ font-size: 50px; }
}
@media only screen and (max-width: 479px){
    .text-effect{ font-size: 36px; }
}
@media only screen and (max-width: 359px){
    .text-effect{ font-size: 27px; }
}
h1 {
  color: #fff;
  font-family: "Bevan", cursive;
  font-size: 4.75em;
  font-weight: normal;
  margin: 0 0 0.5em;
  text-align: center;
  text-shadow: 0.013em 0.039em 0.132em rgba(0, 0, 0, 0.6);
  text-transform: uppercase;
}


h1 {
  text-align: center;
}

.boxed {
    padding-top: 50px;
}

ul {
  width: min(90rem, 90%);
  margin-inline: auto;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(10rem, 1fr));
  justify-content: center;
  gap: 2rem;
  list-style: none;
}

ul li {
  max-width: 12rem;
  justify-self: center;
  display: grid;
  grid-template:
    "icon"
    "line"
    "dot"
    "title"
    "descr" 1fr;
  justify-items: center;
  align-items: flex-start;
  text-align: center;
}

ul li .icon {
  grid-area: icon;
  width: 6rem;
  aspect-ratio: 1;
  display: grid;
  place-items: center;
  color: white;
  font-size: 2.4rem;
  border: 0.3rem solid #89d8f0;
  border-radius: 50%;
  background: var(--accent-color);
  box-shadow: -0.5rem 0.5rem 1rem #89d8f0,
    inset -0.25rem 0.25rem 0.5rem #89d8f0;
}

ul li::before {
  content: "";
  grid-area: line;
  height: 2rem;
  border-right: 2px dotted currentColor;
}

ul li::after {
  content: "";
  grid-area: dot;
  width: 1rem;
  aspect-ratio: 1;
  border-radius: 50%;
  background: var(--accent-color);
  justify-self: center;
  margin-bottom: 0.5rem;
}

ul li .title {
  grid-area: title;
  margin-block: 0.5rem;
  font-size: 1.1rem;
  font-weight: 600;
  text-align: center;
  text-transform: uppercase;
}

.credits {
  position: fixed;
  bottom: 1rem;
  right: 1rem;
}
.credits a {
  color: var(--color);
}

</style>
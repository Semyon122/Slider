let images = [
  {
   url: "./image/Rostov-on-DonAdmiral.png",
   title: "Rostov-on-Don Admiral"
}, {
   url: "./image/SochiThieves.png",
   title: "Sochi Thieves"
}, {
   url: "./image/Rostov-on-DonPatriotic.png",
   title: "Rostov-on-Don Patriotic"
}];

let sliderImages;
let sliderArrows;


function initSlider() {
  if(!images || !images.length) return;

sliderImages = document.querySelector(".slider__images")
sliderArrows = document.querySelector(".slider__arrows")
sliderBalls = document.querySelector(".slider__balls")
sliderCharacteristic = document.querySelector(".slider_characteristic")
}

  initSlider();
  initImages();
  initArrows();
  initBalls();



function initImages() {
  images.forEach((image, index) => {
    let ImageDiv = `<div class ="image n${index} ${index === 0? "active" : ""}" style="background-image: url(${images[index].url});" data-index = "${index}"></div>`;
    sliderImages.innerHTML += ImageDiv;
  });
}

function initArrows() {
  sliderArrows.querySelectorAll(".slider__arrow").forEach(arrow => {
    arrow.addEventListener("click", function() {
      let curNumber = +sliderImages.querySelector(".active").dataset.index;
      let nextNumber;
      if (arrow.classList.contains("left")) {
        nextNumber = curNumber === 0? images.length - 1 : curNumber - 1;
      } else {
        nextNumber = curNumber === images.length - 1? 0 : curNumber + 1;
      }
      moveSlider(nextNumber);
    });
  });
}

function initBalls() {
  images.forEach((image, index) => {
    let ball = `<div class="slider__balls-item n${index} ${index === 0? "active" : ""}" data-index="${index}"></div>`;
    sliderBalls.innerHTML += ball;
  });
  sliderBalls.querySelectorAll(".slider__balls-item").forEach(ball => {
    ball.addEventListener("click", function() {
      moveSlider(this.dataset.index);
    })
  })
}


function moveSlider(num) {
  sliderImages.querySelector(".active").classList.remove("active");
  sliderImages.querySelector(".n" + num).classList.add("active");
}


document.addEventListener ("DOMContentLoaded", initSlider);

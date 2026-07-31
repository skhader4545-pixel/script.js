# script.js
// Play background music
function playMusic() {
    const music = document.getElementById("music");

    music.play().catch(() => {
        console.log("Autoplay blocked until user interaction.");
    });

    document.querySelector(".hero").scrollIntoView({
        behavior: "smooth"
    });
}

// Floating hearts
setInterval(() => {

    const heart = document.createElement("div");

    heart.innerHTML = "❤️";

    heart.style.position = "fixed";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.top = "-20px";
    heart.style.fontSize = (20 + Math.random() * 30) + "px";
    heart.style.opacity = "0.8";
    heart.style.pointerEvents = "none";
    heart.style.transition = "transform 8s linear, opacity 8s";

    document.body.appendChild(heart);

    setTimeout(() => {
        heart.style.transform = "translateY(110vh)";
        heart.style.opacity = "0";
    }, 100);

    setTimeout(() => {
        heart.remove();
    }, 8500);

}, 400);

// Proposal button
document.querySelector(".yes").addEventListener("click", () => {

    alert("❤️ Thank You Safa ❤️\n\nYou are my today, tomorrow and forever.\n\nI Love You So Much ❤️");

    for (let i = 0; i < 100; i++) {

        const heart = document.createElement("div");

        heart.innerHTML = "💖";

        heart.style.position = "fixed";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.top = Math.random() * 100 + "vh";
        heart.style.fontSize = (20 + Math.random() * 35) + "px";
        heart.style.pointerEvents = "none";

        document.body.appendChild(heart);

        setTimeout(() => {
            heart.remove();
        }, 3000);
    }
});

// Gallery auto scroll
const slider = document.querySelector(".slider");

setInterval(() => {

    slider.scrollBy({
        left: 300,
        behavior: "smooth"
    });

    if (slider.scrollLeft + slider.clientWidth
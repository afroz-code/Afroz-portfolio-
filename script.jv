/* PAGE LOAD */
window.addEventListener("load", () => {
  document.body.classList.add("loaded");
});

/* TYPING EFFECT */
const texts = [
  "Frontend Developer",
  "HTML • CSS • JavaScript",
  "Learning Every Day 🚀"
];

let textIndex = 0;
let charIndex = 0;
const typing = document.querySelector(".typing");

function type() {
  if (charIndex < texts[textIndex].length) {
    typing.textContent += texts[textIndex][charIndex++];
    setTimeout(type, 100);
  } else {
    setTimeout(erase, 1500);
  }
}

function erase() {
  if (charIndex > 0) {
    typing.textContent = texts[textIndex].substring(0, --charIndex);
    setTimeout(erase, 60);
  } else {
    textIndex = (textIndex + 1) % texts.length;
    setTimeout(type, 300);
  }
}
type();

/* DARK MODE */
const toggle = document.getElementById("themeToggle");

if (localStorage.getItem("theme") === "dark") {
  document.body.classList.add("dark-mode");
  toggle.textContent = "☀️";
}

toggle.onclick = () => {
  document.body.classList.toggle("dark-mode");
  toggle.textContent = document.body.classList.contains("dark-mode") ? "☀️" : "🌙";
  localStorage.setItem(
    "theme",
    document.body.classList.contains("dark-mode") ? "dark" : "light"
  );
};

/* MOBILE MENU */
function toggleMenu() {
  document.getElementById("navLinks").classList.toggle("show");
}

/* SCROLL ANIMATION */
const reveal = document.querySelectorAll(".section, .card");

window.addEventListener("scroll", () => {
  reveal.forEach(el => {
    if (el.getBoundingClientRect().top < window.innerHeight - 100) {
      el.classList.add("show");
    }
  });
});

/* ACTIVE NAV */
const sections = document.querySelectorAll("section");
const links = document.querySelectorAll(".nav-links a");

window.addEventListener("scroll", () => {
  let current = "";
  sections.forEach(sec => {
    if (scrollY >= sec.offsetTop - 120) {
      current = sec.id;
    }
  });

  links.forEach(a => {
    a.classList.toggle("active", a.getAttribute("href") === `#${current}`);
  });
});

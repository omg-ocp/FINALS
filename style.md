/* Reset and Base Styles - Remove all black space */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html, body {
    margin: 0;
    padding: 0;
    width: 100%;
    min-height: 100vh;
    overflow-x: hidden;
    background: #050508;
    scroll-behavior: smooth;
}

/* Movie Details Modal */
.movie-modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 1000;
    display: flex;
    justify-content: center;
    align-items: center;
    opacity: 0;
    visibility: hidden;
    transition: all 0.3s ease;
}

.movie-modal.active {
    opacity: 1;
    visibility: visible;
}

.modal-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.85);
    backdrop-filter: blur(5px);
}

.modal-content {
    position: relative;
    background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f0f23 100%);
    border-radius: 15px;
    max-width: 900px;
    width: 90%;
    max-height: 90vh;
    overflow-y: auto;
    box-shadow: 0 0 50px rgba(138, 43, 226, 0.3), 0 0 100px rgba(75, 0, 130, 0.2);
    border: 1px solid rgba(138, 43, 226, 0.3);
    transform: scale(0.9);
    transition: transform 0.3s ease;
}

.movie-modal.active .modal-content {
    transform: scale(1);
}

.modal-close {
    position: absolute;
    top: 15px;
    right: 20px;
    font-size: 2.5rem;
    color: rgba(255, 255, 255, 0.7);
    background: none;
    border: none;
    cursor: pointer;
    z-index: 10;
    transition: all 0.3s ease;
    line-height: 1;
}

.modal-close:hover {
    color: white;
    transform: rotate(90deg);
}

.modal-body {
    display: flex;
    padding: 30px;
    gap: 30px;
}

.modal-poster {
    flex-shrink: 0;
    width: 280px;
    margin-top: 10px;
}

.modal-poster img {
    width: 100%;
    height: auto;
    border-radius: 10px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
}

.modal-details {
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 12px;
}

.modal-title {
    font-family: 'Anton', sans-serif;
    font-size: 2.5rem;
    color: white;
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 15px;
    text-shadow: 0 0 20px rgba(138, 43, 226, 0.5);
}

.detail-item {
    font-family: 'Rajdhani', sans-serif;
    font-size: 1.05rem;
    font-weight: 500;
    color: rgba(255, 255, 255, 0.9);
    line-height: 1.5;
}

.detail-label {
    font-weight: 700;
    color: rgba(180, 130, 255, 1);
    margin-right: 8px;
}

.detail-item a {
    color: rgba(100, 200, 255, 1);
    text-decoration: none;
    transition: color 0.3s ease;
}

.detail-item a:hover {
    color: rgba(180, 130, 255, 1);
    text-decoration: underline;
}

@media (max-width: 768px) {
    .modal-body {
        flex-direction: column;
        align-items: center;
    }
    
    .modal-poster {
        width: 200px;
    }
    
    .modal-title {
        font-size: 1.8rem;
        text-align: center;
    }
}

/* Hero Title Section */
.hero-section {
    width: 100%;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background: #050508;
    position: relative;
    overflow: hidden;
    perspective: 1000px;
}

/* Deep Nebula space background - Darker */


@keyframes nebulaMove3D {
    0% { 
        transform: scale(1) rotate(0deg) translateZ(0px); 
        opacity: 1; 
    }
    25% { 
        transform: scale(1.15) rotate(1deg) translateZ(50px) translateX(-20px); 
        opacity: 0.9; 
    }
    50% { 
        transform: scale(1.1) rotate(-1deg) translateZ(30px) translateY(20px); 
        opacity: 0.95; 
    }
    75% { 
        transform: scale(1.2) rotate(2deg) translateZ(60px) translateX(20px); 
        opacity: 0.85; 
    }
    100% { 
        transform: scale(1) rotate(0deg) translateZ(0px); 
        opacity: 1; 
    }
}

/* Secondary nebula layer for depth */
.nebula-layer-2 {
    position: absolute;
    top: -30%;
    left: -30%;
    width: 160%;
    height: 160%;

    transform-style: preserve-3d;
    pointer-events: none;
}

@keyframes nebulaLayer2 {
    0% { 
        transform: scale(1) rotate(0deg) translateZ(-20px); 
    }
    50% { 
        transform: scale(1.3) rotate(-3deg) translateZ(40px) translateX(-30px) translateY(20px); 
    }
    100% { 
        transform: scale(1) rotate(0deg) translateZ(-20px); 
    }
}

/* Stars layer - More dynamic */
.stars {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: 
        radial-gradient(2px 2px at 20px 30px, rgba(255,255,255,0.9), transparent),
        radial-gradient(2px 2px at 40px 70px, rgba(255,255,255,0.8), transparent),
        radial-gradient(1px 1px at 90px 40px, rgba(255,255,255,0.7), transparent),
        radial-gradient(2px 2px at 160px 120px, rgba(255,255,255,0.9), transparent),
        radial-gradient(1px 1px at 230px 80px, rgba(255,255,255,0.6), transparent),
        radial-gradient(3px 3px at 300px 150px, rgba(200,180,255,0.9), transparent),
        radial-gradient(1px 1px at 350px 200px, rgba(255,255,255,0.7), transparent),
        radial-gradient(2px 2px at 420px 60px, rgba(255,255,255,0.9), transparent),
        radial-gradient(1px 1px at 500px 180px, rgba(255,255,255,0.6), transparent),
        radial-gradient(2px 2px at 580px 90px, rgba(180,150,255,0.8), transparent),
        radial-gradient(1px 1px at 650px 250px, rgba(255,255,255,0.7), transparent),
        radial-gradient(3px 3px at 720px 40px, rgba(200,180,255,0.9), transparent),
        radial-gradient(2px 2px at 100px 300px, rgba(255,255,255,0.8), transparent),
        radial-gradient(1px 1px at 200px 350px, rgba(255,255,255,0.6), transparent),
        radial-gradient(2px 2px at 450px 280px, rgba(180,150,255,0.7), transparent);
    background-size: 800px 400px;
    animation: starsTwinkle 3s ease-in-out infinite, starsMove 30s linear infinite;
}

@keyframes starsTwinkle {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.6; }
}

@keyframes starsMove {
    0% { transform: translateX(0) translateY(0); }
    100% { transform: translateX(-50px) translateY(-30px); }
}

/* Marvel Studios Logo - Side by Side */
.marvel-studios-logo {
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: 8px;
    margin-top: 40px;
    margin-bottom: -40px;
    z-index: 15;
    animation: floatLogo 4s ease-in-out infinite;
}

@keyframes floatLogo {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-8px); }
}

.marvel-box {
    background: linear-gradient(180deg, #ED1D24 0%, #B81D24 100%);
    padding: 4px 12px;
    border-radius: 2px;
    box-shadow: 
        0 2px 15px rgba(237, 29, 36, 0.6),
        0 0 30px rgba(237, 29, 36, 0.3),
        inset 0 1px 0 rgba(255,255,255,0.3);
}

.marvel-box span {
    font-family: 'Anton', sans-serif;
    font-size: 0.9rem;
    color: white;
    letter-spacing: 3px;
    font-weight: 400;
}

.studios-text {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 0.9rem;
    color: rgba(255, 255, 255, 0.9);
    letter-spacing: 4px;
}

/* Title Container with Logo Image */
.title-container {
    text-align: center;
    z-index: 10;
    position: relative;
    animation: logoFloat 5s ease-in-out infinite;
    transform-style: preserve-3d;
}

@keyframes logoFloat {
    0%, 100% { 
        transform: translateY(0) rotateX(0deg) scale(1); 
    }
    25% { 
        transform: translateY(-15px) rotateX(2deg) scale(1.02); 
    }
    50% { 
        transform: translateY(-5px) rotateX(0deg) scale(1.01); 
    }
    75% { 
        transform: translateY(-12px) rotateX(-2deg) scale(1.02); 
    }
}

.logo-image {
    max-width: 100%;
    width: clamp(350px, 70vw, 900px);
    height: auto;
    filter: drop-shadow(0 0 50px rgba(138, 43, 226, 0.6))
            drop-shadow(0 0 100px rgba(75, 0, 130, 0.5))
            drop-shadow(0 0 150px rgba(100, 0, 180, 0.3));
    animation: logoGlow 3s ease-in-out infinite alternate, logoPulse 6s ease-in-out infinite;
}

@keyframes logoGlow {
    0% {
        filter: drop-shadow(0 0 50px rgba(138, 43, 226, 0.6))
                drop-shadow(0 0 100px rgba(75, 0, 130, 0.5))
                drop-shadow(0 0 150px rgba(100, 0, 180, 0.3));
    }
    100% {
        filter: drop-shadow(0 0 70px rgba(138, 43, 226, 0.8))
                drop-shadow(0 0 120px rgba(75, 0, 130, 0.6))
                drop-shadow(0 0 180px rgba(100, 0, 180, 0.4));
    }
}

@keyframes logoPulse {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1); }
}

/* Enter Button - Avengers Style */
.enter-button {
    margin-top: 40px;
    z-index: 10;
    position: relative;
}

.enter-btn {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1rem;
    letter-spacing: 3px;
    color: white;
    text-decoration: none;
    display: inline-block;
    background: linear-gradient(135deg, 
        rgba(138, 43, 226, 0.3) 0%, 
        rgba(75, 0, 130, 0.5) 50%, 
        rgba(138, 43, 226, 0.3) 100%);
    border: 2px solid rgba(138, 43, 226, 0.8);
    padding: 12px 35px;
    cursor: pointer;
    position: relative;
    overflow: hidden;
    clip-path: polygon(
        0% 50%, 
        5% 0%, 
        95% 0%, 
        100% 50%, 
        95% 100%, 
        5% 100%
    );
    transition: all 0.4s ease;
    box-shadow: 
        0 0 30px rgba(138, 43, 226, 0.4),
        0 0 60px rgba(75, 0, 130, 0.2),
        inset 0 0 30px rgba(138, 43, 226, 0.1);
    animation: buttonPulse 3s ease-in-out infinite;
}

@keyframes buttonPulse {
    0%, 100% {
        box-shadow: 
            0 0 30px rgba(138, 43, 226, 0.4),
            0 0 60px rgba(75, 0, 130, 0.2),
            inset 0 0 30px rgba(138, 43, 226, 0.1);
    }
    50% {
        box-shadow: 
            0 0 50px rgba(138, 43, 226, 0.6),
            0 0 80px rgba(75, 0, 130, 0.3),
            inset 0 0 40px rgba(138, 43, 226, 0.2);
    }
}

.enter-btn::before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(90deg, 
        transparent, 
        rgba(255, 255, 255, 0.3), 
        transparent);
    transition: left 0.5s ease;
}

.enter-btn:hover::before {
    left: 100%;
}

.enter-btn:hover {
    background: linear-gradient(135deg, 
        rgba(138, 43, 226, 0.5) 0%, 
        rgba(75, 0, 130, 0.7) 50%, 
        rgba(138, 43, 226, 0.5) 100%);
    border-color: rgba(180, 130, 255, 1);
    transform: scale(1.05) translateY(-3px);
    box-shadow: 
        0 0 50px rgba(138, 43, 226, 0.7),
        0 0 100px rgba(75, 0, 130, 0.4),
        0 10px 40px rgba(0, 0, 0, 0.3);
    text-shadow: 0 0 20px rgba(255, 255, 255, 0.5);
}

.enter-btn:active {
    transform: scale(0.98);
}

/* Hexagon decorations on button */
.enter-btn::after {
    content: '';
    position: absolute;
    top: 50%;
    left: 15px;
    transform: translateY(-50%);
    width: 8px;
    height: 8px;
    background: rgba(138, 43, 226, 0.8);
    clip-path: polygon(50% 0%, 100% 25%, 100% 75%, 50% 100%, 0% 75%, 0% 25%);
    box-shadow: 0 0 10px rgba(138, 43, 226, 0.8);
}

/* Glowing line effect */
.glow-line {
    width: 50%;
    max-width: 450px;
    height: 1px;
    background: linear-gradient(90deg, 
        transparent, 
        rgba(138, 43, 226, 0.6), 
        rgba(180, 130, 220, 0.8),
        rgba(138, 43, 226, 0.6),
        transparent
    );
    margin: 50px auto 0;
    box-shadow: 
        0 0 15px rgba(138, 43, 226, 0.5),
        0 0 30px rgba(138, 43, 226, 0.3);
    animation: lineGlow 2s ease-in-out infinite alternate;
}

@keyframes lineGlow {
    0% { opacity: 0.7; width: 45%; }
    100% { opacity: 1; width: 55%; }
}

/* Floating particles effect */
.particles {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
    pointer-events: none;
}

.particle {
    position: absolute;
    width: 3px;
    height: 3px;
    background: rgba(180, 130, 255, 0.7);
    border-radius: 50%;
    box-shadow: 0 0 10px rgba(180, 130, 255, 0.9);
    animation: particleFloat 18s infinite ease-in-out;
}

.particle:nth-child(1) { left: 10%; top: 20%; animation-delay: 0s; width: 2px; height: 2px; }
.particle:nth-child(2) { left: 20%; top: 80%; animation-delay: 2s; }
.particle:nth-child(3) { left: 30%; top: 40%; animation-delay: 4s; width: 4px; height: 4px; }
.particle:nth-child(4) { left: 50%; top: 60%; animation-delay: 1s; }
.particle:nth-child(5) { left: 70%; top: 30%; animation-delay: 3s; width: 2px; height: 2px; }
.particle:nth-child(6) { left: 80%; top: 70%; animation-delay: 5s; }
.particle:nth-child(7) { left: 90%; top: 50%; animation-delay: 2.5s; width: 4px; height: 4px; }
.particle:nth-child(8) { left: 15%; top: 60%; animation-delay: 1.5s; }
.particle:nth-child(9) { left: 85%; top: 25%; animation-delay: 3.5s; width: 2px; height: 2px; }
.particle:nth-child(10) { left: 45%; top: 85%; animation-delay: 4.5s; }
.particle:nth-child(11) { left: 65%; top: 15%; animation-delay: 0.5s; width: 3px; height: 3px; }
.particle:nth-child(12) { left: 5%; top: 45%; animation-delay: 2.8s; }
.particle:nth-child(13) { left: 95%; top: 35%; animation-delay: 1.2s; width: 2px; height: 2px; }
.particle:nth-child(14) { left: 35%; top: 90%; animation-delay: 3.8s; }
.particle:nth-child(15) { left: 75%; top: 10%; animation-delay: 0.8s; width: 3px; height: 3px; }

@keyframes particleFloat {
    0%, 100% {
        transform: translateY(0) translateX(0) scale(1) rotateZ(0deg);
        opacity: 0.4;
    }
    25% {
        transform: translateY(-80px) translateX(30px) scale(1.3) rotateZ(90deg);
        opacity: 0.9;
    }
    50% {
        transform: translateY(-150px) translateX(-20px) scale(1.6) rotateZ(180deg);
        opacity: 1;
    }
    75% {
        transform: translateY(-80px) translateX(-40px) scale(1.3) rotateZ(270deg);
        opacity: 0.7;
    }
}

/* Cosmic dust overlay */
.cosmic-dust {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: 
        radial-gradient(circle at 30% 40%, rgba(120, 0, 180, 0.15) 0%, transparent 25%),
        radial-gradient(circle at 70% 60%, rgba(100, 30, 180, 0.15) 0%, transparent 25%),
        radial-gradient(circle at 50% 80%, rgba(80, 0, 150, 0.1) 0%, transparent 20%);
    pointer-events: none;
    animation: dustFloat3D 20s ease-in-out infinite;
    transform-style: preserve-3d;
}

@keyframes dustFloat3D {
    0% { transform: translateX(0) translateY(0) translateZ(0) rotate(0deg); }
    33% { transform: translateX(40px) translateY(-30px) translateZ(30px) rotate(2deg); }
    66% { transform: translateX(-30px) translateY(20px) translateZ(-20px) rotate(-2deg); }
    100% { transform: translateX(0) translateY(0) translateZ(0) rotate(0deg); }
}

/* Moving light beam */
.light-beam {
    position: absolute;
    top: 0;
    left: -100%;
    width: 50%;
    height: 100%;
    background: linear-gradient(90deg, 
        transparent 0%,
        rgba(138, 43, 226, 0.03) 40%,
        rgba(138, 43, 226, 0.08) 50%,
        rgba(138, 43, 226, 0.03) 60%,
        transparent 100%);
    animation: lightBeamMove 8s linear infinite;
    pointer-events: none;
    transform: skewX(-20deg);
}

@keyframes lightBeamMove {
    0% { left: -100%; }
    100% { left: 200%; }
}

/* Responsive adjustments */
@media (max-width: 768px) {
    .marvel-box span {
        font-size: 0.75rem;
        letter-spacing: 2px;
    }
    .studios-text {
        font-size: 0.75rem;
        letter-spacing: 3px;
    }
    .marvel-studios-logo {
        gap: 6px;
    }
    .logo-image {
        width: clamp(280px, 85vw, 500px);
    }
    .enter-btn {
        font-size: 1.1rem;
        padding: 15px 40px;
        letter-spacing: 3px;
    }
}

@media (max-width: 480px) {
    .logo-image {
        width: clamp(250px, 90vw, 350px);
    }
    .enter-btn {
        font-size: 1rem;
        padding: 12px 30px;
        letter-spacing: 2px;
    }
    .glow-line {
        width: 70%;
    }
}

/* ===== HOME SECTION ===== */
.home-section {
    width: 100%;
    min-height: 100vh;
    background: transparent;
    position: relative;
    display: flex;
    flex-direction: column;
}

/* Home Section Background Image */
#home.home-section {
    background: url('img src/homebg.png') center center / cover no-repeat;
}

/* Iron Man Effect Image - Right Side of Home Section */
.home-side-image {
    position: absolute;
    right: -290px;
    top: 290px;
    height: 90%;
    max-height: 800px;
    width: auto;
    opacity: 1;
    z-index: 1000;
    pointer-events: none;
    object-fit: contain;
}

/* Allow home section content to overflow into next section */
#home.home-section {
    overflow: visible;
    overflow-x: clip;
}

/* Section Side Images - Effect images on right side */
.section-side-image {
    position: absolute;
    right: 0px;
    top: 290px;
    height: 80%;
    max-height: 800px;
    width: auto;
    opacity: 1;
    z-index: 1000;
    pointer-events: none;
    object-fit: contain;
}

/* Hulk on left side for About section - tilted and positioned between home and about */
#about .section-side-image {
    right: auto;
    left: -40px;
    top: 38vh;
    transform: rotate(-20deg);
    z-index: 2;
}

/* Thor on left side for Gallery section */
#gallery .section-side-image {
    right: auto;
    left: 0px;
    height: 110%;
    max-height: 950px;
}

/* Captain America - move more to the right (off screen) */
#cast .section-side-image {
    right: 50px;
    height: 160%;
    max-height: 1500px;
    z-index: 20;
}

/* Gallery section content on top of Captain America */
#gallery .home-content {
    position: relative;
    z-index: 25;
}

/* Allow sections to overflow content but clip horizontal */
#about.home-section,
#cast.home-section,
#gallery.home-section,
#reviews.home-section {
    overflow: visible;
    overflow-x: clip;
}

/* Background overlay with avengers.jpg - Spans About to half of Gallery */
.home-bg-overlay {
    position: absolute;
    top: 72vh;
    left: -100px;
    width: 40%;
    height: 250vh;
    background: url('img src/avengers.jpg') left top / 100% 280vh no-repeat;
    opacity: 0.40;
    z-index: 0;
    filter: blur(2px);
    pointer-events: none;
}

/* Dark overlay for better readability */
body {
    background: #000;
}

/* Navigation Bar - Inside Rectangle */
.rectangle-nav {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 10;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 20px 30px;
    background: linear-gradient(180deg, rgba(0, 0, 0, 0.8) 0%, transparent 100%);
}

.nav-links {
    display: flex;
    list-style: none;
    gap: 25px;
    align-items: center;
}

.nav-logo-item {
    display: flex;
    align-items: center;
    position: relative;
    top: 22px;
    left: 88px;
}

.nav-logo {
    display: flex;
    align-items: center;
    text-decoration: none;
}

.mvs-logo {
    height: 25px;
    width: auto;
    object-fit: contain;
}

.nav-link {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.6rem;
    color: rgba(255, 255, 255, 0.8);
    text-decoration: none;
    letter-spacing: 2px;
    transition: all 0.3s ease;
    position: relative;
    display: flex;
    align-items: center;
    top: 20px;
    left: 105px;
    cursor: pointer;
}

.nav-text {
    position: relative;
}

/* Thunder icon - hidden by default, positioned upper right for hammer drop effect */
.thunder-icon {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(100%, -300%) scale(0.5) rotate(25deg);
    width: 50px;
    height: 45px;
    opacity: 0;
    transition: all 0.3s ease;
    filter: drop-shadow(0 0 5px rgba(255, 255, 100, 0.8));
    pointer-events: none;
}

/* Thor's Hammer Strike Animation - coming from upper right */
@keyframes thorHammerStrike {
    0% {
        opacity: 0;
        transform: translate(150%, -300%) scale(0.8) rotate(35deg);
        filter: drop-shadow(0 0 10px rgba(255, 255, 255, 0.5));
    }
    15% {
        opacity: 1;
        transform: translate(50%, -150%) scale(1) rotate(20deg);
        filter: drop-shadow(0 0 20px rgba(69, 205, 255, 0.8)) drop-shadow(0 0 40px rgba(255, 255, 255, 0.6));
    }
    30% {
        transform: translate(-50%, -50%) scale(1.3) rotate(5deg);
        filter: drop-shadow(0 0 30px rgba(69, 205, 255, 1)) drop-shadow(0 0 60px rgba(255, 255, 255, 0.8));
    }
    40% {
        transform: translate(-50%, -40%) scale(1.4) rotate(-5deg);
        filter: drop-shadow(0 0 50px rgba(69, 205, 255, 1)) drop-shadow(0 0 80px rgba(255, 255, 255, 1)) drop-shadow(0 0 100px rgba(69, 205, 255, 0.8));
    }
    50% {
        transform: translate(-50%, -50%) scale(1.2) rotate(0deg);
        filter: drop-shadow(0 0 40px rgba(69, 205, 255, 1)) drop-shadow(0 0 70px rgba(255, 255, 255, 0.9));
    }
    70% {
        transform: translate(-50%, -55%) scale(1.1) rotate(3deg);
        filter: drop-shadow(0 0 25px rgba(69, 205, 255, 0.9)) drop-shadow(0 0 50px rgba(255, 255, 255, 0.7));
    }
    85% {
        transform: translate(-50%, -48%) scale(1.05) rotate(-2deg);
    }
    100% {
        opacity: 1;
        transform: translate(-50%, -50%) scale(1) rotate(0deg);
        filter: drop-shadow(0 0 15px rgba(69, 205, 255, 0.8)) drop-shadow(0 0 30px rgba(255, 255, 255, 0.5));
    }
}

.nav-link:hover .thunder-icon,
.nav-link.active .thunder-icon {
    opacity: 1;
    animation: thorHammerStrike 0.6s cubic-bezier(0.25, 0.46, 0.45, 0.94) forwards;
}

.nav-link:hover,
.nav-link.active {
    color: #6ab7ff;
}

/* Home Content */
.home-content {
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 40px;
    z-index: 1;
}

/* Rectangle Container */
.home-rectangle {
    width: 1005px;
    height: 80vh;
    left: -130px;
    position: relative;
    border-radius: 10px;
    overflow: hidden;
    background: #a5a5a5;
    box-shadow: 
        0 0 50px rgba(138, 43, 226, 0.3),
        0 0 100px rgba(75, 0, 130, 0.2),
        inset 0 0 100px rgba(0, 0, 0, 0.5);
    border: 1px solid rgba(0, 0, 0, 0.4);
}

/* Right-positioned rectangle for About and Gallery */
.home-rectangle.right {
    left: 130px;
}

/* Image wrapper with gap */
.rectangle-image-wrapper {
    position: absolute;
    top: 15px;
    left: 15px;
    right: 15px;
    bottom: 15px;
    border-radius: 0px;
    overflow: hidden;
    z-index: 0;
}

/* Video background */
.rectangle-video {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    min-width: 100%;
    min-height: 100%;
    width: auto;
    height: auto;
    object-fit: cover;
    z-index: 0;
}

/* Video Dark Overlay - shows when paused */
.video-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    z-index: 1;
    transition: opacity 0.4s ease;
    pointer-events: none;
}

.video-overlay.hidden {
    opacity: 0;
}

/* Video Dim Overlay - shows when paused */
.video-dim-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.4);
    z-index: 5;
    transition: opacity 0.4s ease;
    pointer-events: none;
}

.video-dim-overlay.hidden {
    opacity: 0;
}

/* Video Toggle Button - Centered Transparent Circle */
.video-toggle-btn {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 70px;
    height: 70px;
    border-radius: 50%;
    background: transparent;
    border: 2px solid rgba(255, 255, 255, 0.7);
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 20;
    transition: all 0.3s ease;
    pointer-events: auto;
}

.video-toggle-btn:hover {
    border-color: rgba(255, 255, 255, 1);
    background: rgba(255, 255, 255, 0.1);
    transform: translate(-50%, -50%) scale(1.05);
}

.video-toggle-btn .play-icon,
.video-toggle-btn .pause-icon {
    width: 28px;
    height: 28px;
    color: rgba(255, 255, 255, 0.9);
}

.video-toggle-btn .play-icon {
    margin-left: 4px;
}

/* Video Controls - Progress Bar & Time */
.video-controls {
    position: absolute;
    bottom: 20px;
    left: 20px;
    right: 20px;
    display: flex;
    align-items: center;
    gap: 15px;
    z-index: 20;
    pointer-events: auto;
    opacity: 0;
    transition: opacity 0.3s ease;
}

.rectangle-image-wrapper:hover .video-controls {
    opacity: 1;
    pointer-events: auto;
}

.video-progress-container {
    flex: 1;
    height: 6px;
    background: rgba(255, 255, 255, 0.3);
    border-radius: 3px;
    cursor: pointer;
    overflow: hidden;
}

.video-progress-bar {
    height: 100%;
    width: 0%;
    background: linear-gradient(90deg, rgba(138, 43, 226, 0.9), rgba(180, 130, 255, 0.9));
    border-radius: 3px;
    transition: width 0.1s linear;
}

.video-progress-container:hover .video-progress-bar {
    background: linear-gradient(90deg, rgba(138, 43, 226, 1), rgba(200, 150, 255, 1));
}

.video-time {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 0.9rem;
    color: rgba(255, 255, 255, 0.9);
    letter-spacing: 1px;
    white-space: nowrap;
    text-shadow: 0 0 5px rgba(0, 0, 0, 0.8);
}

/* Video Play/Pause Button - Centered */
.video-play-btn {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 80px;
    height: 80px;
    border-radius: 50%;
    background: rgba(138, 43, 226, 0.8);
    border: 3px solid rgba(255, 255, 255, 0.9);
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 10;
    transition: all 0.3s ease;
}

.video-play-btn:hover {
    background: rgba(138, 43, 226, 1);
    transform: translate(-50%, -50%) scale(1.1);
    box-shadow: 0 0 30px rgba(138, 43, 226, 0.8);
}

.video-play-btn .play-icon-svg,
.video-play-btn .pause-icon-svg {
    width: 36px;
    height: 36px;
    color: white;
}

.video-play-btn .play-icon-svg {
    margin-left: 5px;
}

/* MVS Logo Corner Position for About */
.about-mvs-corner {
    position: absolute;
    top: 45px;
    left: 45px;
    z-index: 15;
}

.about-mvs-corner .mvs-logo {
    height: 30px;
    width: auto;
}

/* About section nav without logo */
.about-nav {
    justify-content: center;
}

.about-nav .nav-links {
    padding-left: 0;
}

.about-nav .nav-link {
    top: 26px;
    left: 160px;
}

/* Cinema Info - Upper Right */
.cinema-info {
    position: absolute;
    top: 150px;
    right: 725px;
    left: 58px;
    text-align: left;
    z-index: 5;
}

.cinema-info p {
    font-family: 'Anton', sans-serif;
    color: white;
    letter-spacing: 3px;
    line-height: 1.3;
    text-transform: uppercase;
    text-shadow: 0 0 15px rgba(0, 0, 0, 0.8);
    margin-bottom: 20px;
}

.cinema-small {
    font-size: 2rem;
}

.cinema-big {
    font-size: 3.5rem;
}

.more-info-btn {
    display: inline-block;
    font-family: 'Rajdhani', sans-serif;
    font-size: 1rem;
    font-weight: 500;
    color: white;
    text-decoration: none;
    letter-spacing: 0.5px;
    padding: 10px 25px;
    background: rgba(151, 151, 151, 0.6);
    border-radius: 30px;
    transition: all 0.3s ease;
    cursor: pointer;
}

.more-info-btn:hover {
    background: rgba(75, 213, 255, 0.9);
    box-shadow: 0 0 20px rgba(138, 43, 226, 0.5);
    transform: translateY(-2px);
}

/* About Description - Lower Right */
.about-description {
    position: absolute;
    bottom: 100px;
    right: 50px;
    z-index: 2;
    left: 350px;
    white-space: nowrap;
}

.about-description p {
    font-family: 'Rajdhani', sans-serif;
    font-size: 1.0rem;
    font-weight: 500;
    color: rgba(255, 255, 255, 0.9);
    letter-spacing: 0.5px;
    line-height: 1.3;
    text-shadow: 0 0 10px rgba(0, 0, 0, 0.8);
}

.rectangle-bg {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: url('img src/home-inside.jpg') center center / cover no-repeat;
    z-index: 0;
}

.rectangle-content {
    position: relative;
    z-index: 1;
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    padding: 50px 0 50px 50px;
    background: linear-gradient(180deg, 
        rgba(0, 0, 0, 0.4) 0%,
        rgba(0, 0, 0, 0.2) 50%,
        rgba(0, 0, 0, 0.6) 100%);
    pointer-events: none;
}

.rectangle-content * {
    pointer-events: auto;
}

.content-left {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 15px;
}

.home-subtitle {
    font-family: 'Anton', sans-serif;
    font-size: 4.5rem;
    font-weight: 400;
    color: white;
    letter-spacing: 4px;
    line-height: 80px;
    text-transform: uppercase;
    text-shadow: 
        0 0 20px rgba(0, 0, 0, 0.8),
        0 0 40px rgba(0, 0, 0, 0.5);
}

/* Trailer Button */
.trailer-btn {
    display: flex;
    align-items: center;
    gap: 10px;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1rem;
    color: white;
    text-decoration: none;
    letter-spacing: 2px;
    padding: 10px 20px;
    background: rgba(3, 14, 81, 0.6);
    border: 1px solid rgba(138, 43, 226, 0.6);
    border-radius: 20px;
    transition: all 0.3s ease;
}

.trailer-btn:hover {
    background: rgba(138, 43, 226, 0.5);
    box-shadow: 0 0 20px rgba(138, 43, 226, 0.4);
}

.play-icon-circle {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 26px;
    height: 26px;
    border: 2px solid white;
    border-radius: 50%;
    background: transparent;
}

.play-icon {
    width: 12px;
    height: 12px;
    margin-left: 2px;
}

/* Placeholder Page Sections */
.page-section {
    width: 100%;
    min-height: 100vh;
    background: #0a0a0a;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
}

.page-section h2 {
    font-family: 'Anton', sans-serif;
    font-size: 3rem;
    color: white;
    letter-spacing: 5px;
}

/* Smooth scroll behavior */
html {
    scroll-behavior: smooth;
}

/* Nav responsive */
@media (max-width: 768px) {
    .rectangle-nav {
        padding: 12px 20px;
    }
    
    .nav-links {
        gap: 20px;
    }
    
    .nav-link {
        font-size: 0.9rem;
    }
    
    .home-title {
        font-size: 2.5rem;
        letter-spacing: 5px;
    }
    
    .home-subtitle {
        font-size: 1.2rem;
        letter-spacing: 5px;
    }
}

@media (max-width: 480px) {
    .nav-links {
        gap: 12px;
    }
    
    .nav-link {
        font-size: 0.75rem;
        letter-spacing: 1px;
    }
    
    .home-rectangle {
        height: 60vh;
    }
    
    .home-title {
        font-size: 1.8rem;
    }
}

/* Cast & Characters Section */
.rectangle-bg.cast-bg {
    background: url('img src/cc.png') center center / cover no-repeat;
    opacity: 0.9;
}

#cast .home-content {
    position: relative;
    z-index: 5;
}

.cast-content {
    justify-content: center !important;
    align-items: center !important;
    overflow: hidden;
}

.cast-section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    z-index: 5;
    width: 95%;
    padding: 20px 0 20px 20px;
    transition: all 0.4s ease;
}

.cast-title {
    font-family: 'Anton', sans-serif;
    font-size: 4rem;
    color: white;
    letter-spacing: 3px;
    text-align: left;
    line-height: 1.1;
    text-transform: uppercase;
    text-shadow: 0 0 20px rgba(0, 0, 0, 0.8);
    margin-bottom: 15px;
    margin-top: 40px;
    margin-left: -20px;
}

.cast-line {
    width: 900px;
    height: 2px;
    background: linear-gradient(90deg, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0.3));
    margin-bottom: 30px;
    align-self: center;
    margin-left: -70px;
}

/* Character Carousel */
.character-carousel {
    display: flex;
    align-items: center;
    width: 110%;
    position: relative;
    margin-bottom: 30px;
    left: -80px;
}

.carousel-btn {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    width: 40px;
    height: 80px;
    background: transparent;
    border: none;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.3s ease;
    z-index: 10;
    outline: none;
}

.carousel-btn:focus {
    outline: none;
}

.carousel-btn:active {
    outline: none;
    box-shadow: none;
}

.carousel-btn.prev-btn {
    left: 50px;
}

.carousel-btn.next-btn {
    right: 50px;
}

.carousel-btn:hover {
    background: transparent;
}

.carousel-btn:hover svg {
    transform: scale(1.3);
    color: #ff0000;
}

.carousel-btn svg {
    width: 35px;
    height: 35px;
    color: #ff0000;
    filter: drop-shadow(0 0 5px rgba(0, 0, 0, 0.8));
    transition: all 0.3s ease;
}

.character-slider {
    display: flex;
    gap: 28px;
    overflow-x: auto;
    scroll-behavior: smooth;
    padding: 30px 50px;
    width: 100%;
    scrollbar-width: none;
    -ms-overflow-style: none;
    cursor: grab;
    margin: -20px 0;
}

.character-slider:active {
    cursor: grabbing;
}

.character-slider::-webkit-scrollbar {
    display: none;
}

.character-item {
    flex-shrink: 0;
    width: 130px;
    height: 180px;
    border-radius: 10px;
    overflow: visible;
    cursor: pointer;
    transition: all 0.3s ease;
}

.character-item:hover {
    transform: scale(1.1);
}

.character-item.selected {
    transform: scale(1.1);
}

.character-item.selected img {
    filter: drop-shadow(0 0 20px rgba(37, 87, 251, 0.8));
}

.character-item img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    transition: filter 0.3s ease;
    filter: drop-shadow(0 0 15px rgba(37, 87, 251, 0.8));
}

.cast-tagline {
    font-family: 'Rajdhani', sans-serif;
    font-size: 1.5rem;
    font-weight: 600;
    color: rgba(255, 255, 255, 0.9);
    letter-spacing: 2px;
    text-align: center;
    text-shadow: 0 0 10px rgba(0, 0, 0, 0.8);
    margin-top: 5px;
}

/* Character Detail View - Option C: 3D Horizontal Carousel */
.character-detail-view {
    position: absolute;
    top: 15px;
    left: 15px;
    right: 0;
    bottom: 0;
    background: transparent;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    z-index: 100;
    opacity: 0;
    visibility: hidden;
    perspective: 1000px;
    transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1);
    overflow: visible;
    margin-right: -54px;
    margin-bottom: 35px;
}

.character-detail-view.active {
    opacity: 1;
    visibility: visible;
    background: transparent;
}

/* Character Info Panel - Right Side */
.character-info-panel {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: center;
    padding: 20px 0 20px 30px;
    width: 70%;
    height: 100%;
    text-align: left;
    opacity: 0;
    transform: translateX(50px);
    transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1) 0.3s;
    overflow-y: auto;
    scrollbar-width: none;
    margin-right: 0;
    margin-top: 40px;
}

.character-info-panel::-webkit-scrollbar {
    display: none;
}

.character-detail-view.active .character-info-panel {
    opacity: 1;
    transform: translateX(-100px);
}

.char-divider-top {
    width: 100%;
    height: 1px;
    background: rgba(255, 255, 255, 1);
    margin-top: 15px;
    margin-bottom: 8px;
}

.char-subtitle {
    font-family: 'Rajdhani', sans-serif;
    font-size: 0.75rem;
    font-weight: 600;
    color: rgba(255, 255, 255, 0.5);
    letter-spacing: 4px;
    text-transform: uppercase;
    margin-bottom: 2px;
}

.char-name-wrapper {
    position: relative;
    display: inline-block;
}

.char-name {
    font-family: 'Anton', sans-serif;
    font-size: 3.5rem;
    color: #ff0000;
    letter-spacing: 2px;
    text-transform: uppercase;
    text-shadow: 0 0 30px rgba(255, 0, 0, 0.5);
    margin-bottom: 6px;
    line-height: 1;
    white-space: nowrap;
    cursor: pointer;
    transition: all 0.3s ease;
}

.char-name:hover {
    color: #ff3333;
}

/* Character Name Hover Preview - Fixed position independent of panel */
.char-name-preview {
    position: fixed;
    bottom: 85px;
    right: 395px;
    width: 350px;
    height: 450px;
    z-index: 9999;
    opacity: 0;
    visibility: hidden;
    transition: opacity 0.4s ease, visibility 0.4s ease;
    pointer-events: none;
    overflow: hidden;
}

.char-name-preview img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    object-position: top center;
    opacity: 0.35;
}

.char-name-preview.visible {
    opacity: 1;
    visibility: visible;
}

.char-divider {
    width: 100%;
    height: 1px;
    background: linear-gradient(90deg, rgba(150, 150, 150, 0.8), rgba(150, 150, 150, 0.3), transparent);
    margin-bottom: 10px;
}

.char-profile-title {
    font-family: 'Rajdhani', sans-serif;
    font-size: 0.7rem;
    font-weight: 600;
    color: rgba(255, 255, 255, 0.4);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 8px;
}

.char-profile-content {
    display: flex;
    flex-direction: column;
    gap: 6px;
    margin-bottom: 10px;
}

.char-info-line {
    font-family: 'Rajdhani', sans-serif;
    font-size: 0.85rem;
    font-weight: 500;
    color: rgba(255, 255, 255, 0.85);
    line-height: 1.5;
}

.info-label {
    color: rgba(255, 100, 100, 1);
    font-weight: 600;
    font-size: 0.85rem;
}

.char-divider-bottom {
    width: 100%;
    height: 1px;
    background: linear-gradient(90deg, rgba(150, 150, 150, 0.8), rgba(150, 150, 150, 0.3), transparent);
    margin-bottom: 10px;
}

.char-movies {
    display: flex;
    gap: 8px;
    position: relative;
    overflow: visible;
}

.movie-thumb-wrapper {
    position: relative;
    overflow: visible;
}

.char-movie-img {
    width: 65px;
    height: 90px;
    object-fit: cover;
    border-radius: 4px;
    border: 1px solid rgba(255, 255, 255, 0.2);
    transition: all 0.3s ease;
    opacity: 0.7;
    cursor: pointer;
}

.char-movie-img:hover {
    border-color: rgba(255, 0, 0, 0.8);
    opacity: 1;
}

/* Movie Preview Popup on Hover */
.movie-preview {
    position: fixed;
    top: 50%;
    right: 20px;
    transform: translateY(-50%) scale(0.8);
    width: 200px;
    height: 300px;
    z-index: 9999;
    opacity: 0;
    visibility: hidden;
    transition: all 0.3s ease;
    pointer-events: none;
}

.movie-preview img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 10px;
    border: 3px solid rgba(255, 0, 0, 0.6);
    box-shadow: 0 0 60px rgba(0, 0, 0, 0.9),
                0 0 40px rgba(255, 0, 0, 0.3);
}

.movie-thumb-wrapper:hover .movie-preview {
    opacity: 1;
    visibility: visible;
    transform: translateY(-50%) scale(1);
}

/* Horizontal 3D Carousel - Left Side */
.horizontal-3d-carousel {
    display: flex;
    align-items: center;
    justify-content: flex-end;
    width: 48%;
    height: 100%;
    position: relative;
    perspective: 1200px;
    opacity: 0;
    transform: translateX(-50px);
    transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1) 0.2s;
    padding-right: 40px;
    overflow: visible;
    -webkit-mask-image: linear-gradient(to right, transparent 0%, black 15%, black 100%);
    mask-image: linear-gradient(to right, transparent 0%, black 15%, black 100%);
    top: 25px;
}

.character-detail-view.active .horizontal-3d-carousel {
    opacity: 1;
    transform: translateX(0);
}

.h3d-btn {
    position: absolute;
    background: transparent;
    border: none;
    cursor: pointer;
    padding: 15px;
    z-index: 20;
    transition: all 0.3s ease;
    outline: none;
}

.h3d-btn.prev-btn {
    left: 20px;
}

.h3d-btn.next-btn {
    right: 80px;
}

.h3d-btn svg {
    width: 40px;
    height: 40px;
    color: rgba(255, 255, 255, 0.6);
    filter: drop-shadow(0 0 10px rgba(0, 0, 0, 0.8));
    transition: all 0.3s ease;
}

.h3d-btn:hover svg {
    color: #ff0000;
    transform: scale(1.3);
    filter: drop-shadow(0 0 15px rgba(255, 0, 0, 0.5));
}

.h3d-stage {
    width: 450px;
    height: 380px;
    position: relative;
    transform-style: preserve-3d;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: visible;
}

.h3d-slider {
    position: relative;
    width: 100%;
    height: 100%;
    transform-style: preserve-3d;
    transition: transform 0.6s cubic-bezier(0.4, 0, 0.2, 1);
}

.h3d-char-item {
    position: absolute;
    width: 180px;
    height: 250px;
    left: 50%;
    top: 50%;
    margin-left: -90px;
    margin-top: -125px;
    cursor: pointer;
    transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1);
    transform-style: preserve-3d;
}

.h3d-char-item img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    transition: all 0.5s ease;
    filter: blur(3px) brightness(0.4) grayscale(0.3);
}

.h3d-char-item:hover img {
    filter: blur(1.5px) brightness(0.6) grayscale(0.1);
}

.h3d-char-item.active {
    z-index: 100 !important;
}

.h3d-char-item.active img {
    filter: blur(0) brightness(1) grayscale(0) drop-shadow(0 0 40px rgba(255, 0, 0, 0.9));
    animation: cardGlow 2s ease-in-out infinite;
}

@keyframes cardGlow {
    0%, 100% { filter: blur(0) brightness(1) grayscale(0) drop-shadow(0 0 40px rgba(255, 0, 0, 0.9)); }
    50% { filter: blur(0) brightness(1.1) grayscale(0) drop-shadow(0 0 60px rgba(255, 50, 50, 1)); }
}

/* ===== GALLERY SECTION ===== */
.gallery-wrapper {
    position: absolute;
    top: 15px;
    left: 15px;
    right: 15px;
    bottom: 15px;
    overflow: hidden;
}

.gallery-video-bg {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
    z-index: 0;
}

.gallery-video-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    z-index: 1;
}

.gallery-content {
    justify-content: flex-start !important;
    align-items: stretch !important;
    padding: 80px 50px 50px 50px !important;
    z-index: 2;
    flex-direction: row !important;
}

.gallery-header {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
    margin-bottom: 0;
    height: 100%;
    margin-left: 30px;
    margin-top: 150px;
}

.gallery-title {
    font-family: 'Anton', sans-serif;
    font-size: 2.5em;
    color: white;
    letter-spacing: 3px;
    text-transform: uppercase;
    text-shadow: 0 0 20px rgba(0, 0, 0, 0.8);
    margin: 0;
    line-height: 1;
    writing-mode: vertical-lr;
    transform: rotate(180deg);
}

.gallery-line {
    width: 2px;
    height: 140px;
    background: linear-gradient(180deg, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0.1));
}

.gallery-carousel {
    flex: 1;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-end;
    padding-top: 80px;
}

.gallery-slides {
    display: flex;
    gap: 20px;
    align-items: center;
    justify-content: flex-end;
    margin-right: 22px;
}

.gallery-item {
    border-radius: 0;
    overflow: hidden;
    cursor: pointer;
    transition: all 0.4s ease;
}

.gallery-item img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: all 0.4s ease;
}

.gallery-item.main-item {
    width: 215px;
    height: 280px;
    border: 2px solid rgba(138, 43, 226, 0.8);
    box-shadow: 0 0 40px rgba(138, 43, 226, 0.4);
    flex-shrink: 0;
}

.gallery-item.main-item:hover {
    transform: scale(1.02);
    border-color: rgba(138, 43, 226, 1);
    box-shadow: 0 0 50px rgba(138, 43, 226, 0.6);
}

.gallery-item.side-item {
    width: 160px;
    height: 220px;
    opacity: 1;
    border: 1px solid rgba(255, 255, 255, 0.2);
    flex-shrink: 0;
}

.gallery-item.side-item:hover {
    opacity: 1;
    transform: scale(1.05);
    border-color: rgba(255, 255, 255, 0.5);
}

.gallery-nav {
    display: flex;
    gap: 0px;
    justify-content: flex-end;
    align-items: center;
    padding-right: 10px;
    margin-top: 40px;
}

.gallery-btn {
    width: 40px;
    height: 40px;
    background: transparent;
    border: none;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.3s ease;
    padding: 0;
    padding-bottom: 20px;
}

.gallery-btn:hover {
    transform: scale(1.2);
}

.gallery-btn:active {
    transform: scale(1.3);
}

.gallery-btn svg {
    width: 30px;
    height: 30px;
    color: rgba(255, 255, 255, 0.7);
    transition: all 0.3s ease;
}

.gallery-btn.gallery-next svg {
    color: #ff0000;
}

.gallery-btn:hover svg {
    color: #ff0000;
}

.gallery-btn:active svg {
    color: #ff0000;
}

/* ===== REVIEWS SECTION ===== */
.rectangle-bg.reviews-bg {
    background: url('img src/reviewsbg.jpg') center center / cover no-repeat;
}

.reviews-content {
    justify-content: flex-start !important;
    align-items: flex-end !important;
    padding: 120px 50px 80px 50px !important;
    z-index: 5;
}

.reviews-panel {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    max-width: 500px;
    text-align: right;
    z-index: 10;
    margin-right: 30px;
}

.reviewer-name {
    font-family: 'Anton', sans-serif;
    font-size: 2.5rem;
    color: white;
    letter-spacing: 2px;
    text-transform: uppercase;
    text-shadow: 0 0 20px rgba(0, 0, 0, 0.8);
    margin: 0 0 20px 0;
    line-height: 1.2;
}

.genre-tags {
    display: flex;
    gap: 10px;
    margin-bottom: 15px;
    justify-content: flex-end;
}

.genre-tag {
    font-family: 'Rajdhani', sans-serif;
    font-size: 0.85rem;
    font-weight: 600;
    color: white;
    background: rgba(59, 130, 246, 0.8);
    padding: 6px 18px;
    border-radius: 50px;
    letter-spacing: 1px;
}

.movie-info {
    font-family: 'Rajdhani', sans-serif;
    font-size: 0.85rem;
    font-weight: 500;
    color: rgba(180, 180, 180, 1);
    margin-bottom: 20px;
    letter-spacing: 0.5px;
}

.review-text {
    font-family: 'Rajdhani', sans-serif;
    font-size: 1.1rem;
    font-weight: 500;
    color: rgba(255, 255, 255, 0.95);
    line-height: 1.6;
    margin-bottom: 25px;
    text-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
    min-height: 80px;
    max-width: 400px;
}

.reviews-nav {
    display: flex;
    gap: 5px;
    align-items: center;
    margin-top: 10px;
    z-index: 20;
    justify-content: flex-end;
}

.review-btn {
    width: 100px;
    height: 100px;
    background: transparent;
    border: none;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.3s ease;
    padding: 0;
    z-index: 20;
}

.review-btn:hover {
    transform: scale(1.2);
}

.review-btn:active {
    transform: scale(1.3);
}

.review-btn svg {
    width: 35px;
    height: 35px;
    color: rgba(255, 255, 255, 0.9);
    transition: all 0.3s ease;
}

.review-btn.review-next svg {
    color: #ff0000;
}

.review-btn:hover svg {
    color: #ff0000;
}

/* Side navigation buttons */
.review-side-btn {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    width: 50px;
    height: 50px;
}

.review-side-btn.review-prev {
    left: 30px;
}

.review-side-btn.review-next {
    right: 30px;
}

/* Rating Section */
.rating-section {
    display: flex;
    align-items: center;
    gap: 15px;
    margin-bottom: 25px;
    justify-content: flex-end;
}

.heart-icon {
    font-size: 3rem;
    color: #ff4757;
    text-shadow: 0 0 15px rgba(255, 71, 87, 0.8);
    display: flex;
    align-items: center;
    justify-content: center;
}

.rating-info {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
}

.rating-percent {
    font-family: 'Anton', sans-serif;
    font-size: 2rem;
    color: white;
    letter-spacing: 1px;
    text-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
    line-height: 1;
}

.rating-remark {
    font-family: 'Rajdhani', sans-serif;
    font-size: 0.85rem;
    font-weight: 600;
    color: rgba(100, 255, 100, 1);
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-top: 3px;
}

/* Watch Trailer Button in Reviews */
.review-trailer-btn {
    display: flex;
    align-items: center;
    gap: 10px;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1rem;
    color: white;
    text-decoration: none;
    letter-spacing: 2px;
    padding: 10px 25px;
    background: rgba(3, 14, 81, 0.6);
    border: 1px solid rgba(138, 43, 226, 0.6);
    border-radius: 30px;
    transition: all 0.3s ease;
    margin-top: -15px;
}

.review-trailer-btn:hover {
    background: rgba(138, 43, 226, 0.5);
    box-shadow: 0 0 20px rgba(138, 43, 226, 0.4);
}

/* ========================================
   ENHANCED ANIMATIONS & TRANSITIONS
   (Additive only - no overrides)
   ======================================== */

/* ===== KEYFRAMES FOR OPTIONAL USE ===== */
@keyframes fadeInUp {
    from { opacity: 0; transform: translateY(60px); }
    to { opacity: 1; transform: translateY(0); }
}

@keyframes fadeInDown {
    from { opacity: 0; transform: translateY(-60px); }
    to { opacity: 1; transform: translateY(0); }
}

@keyframes fadeInLeft {
    from { opacity: 0; transform: translateX(-60px); }
    to { opacity: 1; transform: translateX(0); }
}

@keyframes fadeInRight {
    from { opacity: 0; transform: translateX(60px); }
    to { opacity: 1; transform: translateX(0); }
}

@keyframes scaleIn {
    from { opacity: 0; transform: scale(0.8); }
    to { opacity: 1; transform: scale(1); }
}

@keyframes blurIn {
    from { opacity: 0; filter: blur(20px); }
    to { opacity: 1; filter: blur(0); }
}

@keyframes glitchIn {
    0% { opacity: 0; transform: translateX(-5px); filter: hue-rotate(90deg); }
    20% { opacity: 0.8; transform: translateX(5px); filter: hue-rotate(-90deg); }
    40% { opacity: 0.6; transform: translateX(-3px); filter: hue-rotate(45deg); }
    60% { opacity: 0.9; transform: translateX(3px); filter: hue-rotate(-45deg); }
    80% { opacity: 1; transform: translateX(-1px); filter: hue-rotate(0deg); }
    100% { opacity: 1; transform: translateX(0); filter: hue-rotate(0deg); }
}

@keyframes heartBeat {
    0%, 100% { transform: scale(1); }
    14% { transform: scale(1.3); }
    28% { transform: scale(1); }
    42% { transform: scale(1.3); }
    70% { transform: scale(1); }
}

@keyframes shimmer {
    0% { background-position: -200% 0; }
    100% { background-position: 200% 0; }
}

/* ===== HEART ICON ANIMATION (Reviews) ===== */
.heart-icon {
    animation: heartBeat 1.5s ease-in-out infinite;
}

/* ===== SCROLLBAR STYLING ===== */
/* Hide scrollbar completely */
::-webkit-scrollbar {
    display: none;
    width: 0;
}

html, body {
    scrollbar-width: none;
    -ms-overflow-style: none;
}

/* ===== TEXT SELECTION STYLING ===== */
::selection {
    background: rgba(138, 43, 226, 0.5);
    color: white;
    text-shadow: 0 0 10px rgba(180, 130, 255, 0.8);
}

::-moz-selection {
    background: rgba(138, 43, 226, 0.5);
    color: white;
    text-shadow: 0 0 10px rgba(180, 130, 255, 0.8);
}

/* ===== BUTTON RIPPLE EFFECT ===== */
.button-ripple {
    position: absolute;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.4);
    transform: scale(0);
    animation: rippleEffect 0.6s ease-out;
    pointer-events: none;
}

@keyframes rippleEffect {
    to {
        transform: scale(4);
        opacity: 0;
    }
}

/* ===== SCROLL ANIMATION CLASSES (JS Applied) ===== */
.animate-on-scroll {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity 0.6s ease, transform 0.6s ease;
}

.animate-on-scroll.animate-visible {
    opacity: 1;
    transform: translateY(0);
}

/* ===== SHIMMER LOADING CLASS ===== */
.loading-shimmer {
    background: linear-gradient(90deg, 
        rgba(255, 255, 255, 0) 0%, 
        rgba(255, 255, 255, 0.1) 50%, 
        rgba(255, 255, 255, 0) 100%);
    background-size: 200% 100%;
    animation: shimmer 1.5s infinite;
}

/* ===== INFINITY STONE CURSOR ===== */
/* Hide default cursor globally */
*, *::before, *::after {
    cursor: none !important;
}

/* Infinity Stone Cursor - Main Orb */
.infinity-cursor {
    position: fixed;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    pointer-events: none;
    z-index: 99999;
    transform: translate(-50%, -50%);
    transition: width 0.15s ease, height 0.15s ease, box-shadow 0.2s ease, background 0.2s ease;
    will-change: left, top, transform;
    /* Default: Power Stone (Purple) */
    background: radial-gradient(circle at 30% 30%, 
        rgba(255, 255, 255, 0.9) 0%, 
        rgba(180, 130, 255, 1) 20%, 
        rgba(138, 43, 226, 1) 50%, 
        rgba(75, 0, 130, 0.9) 100%);
    box-shadow: 
        0 0 15px rgba(138, 43, 226, 0.8),
        0 0 30px rgba(138, 43, 226, 0.6),
        0 0 45px rgba(138, 43, 226, 0.4),
        inset 0 0 10px rgba(255, 255, 255, 0.3);
    animation: stonePulse 1.5s ease-in-out infinite;
}

/* Cursor Trail Effect */
.infinity-cursor::before {
    content: '';
    position: absolute;
    top: 50%;
    left: 50%;
    width: 30px;
    height: 30px;
    border-radius: 50%;
    transform: translate(-50%, -50%);
    background: radial-gradient(circle, rgba(138, 43, 226, 0.3) 0%, transparent 70%);
    animation: trailPulse 1s ease-in-out infinite;
    pointer-events: none;
}

/* Sparkle particles container */
.infinity-cursor::after {
    content: '';
    position: absolute;
    top: 50%;
    left: 50%;
    width: 40px;
    height: 40px;
    transform: translate(-50%, -50%);
    background-image: 
        radial-gradient(2px 2px at 5px 5px, rgba(255, 255, 255, 0.8), transparent),
        radial-gradient(2px 2px at 35px 10px, rgba(255, 255, 255, 0.6), transparent),
        radial-gradient(1px 1px at 20px 35px, rgba(255, 255, 255, 0.7), transparent),
        radial-gradient(2px 2px at 10px 30px, rgba(255, 255, 255, 0.5), transparent);
    opacity: 0;
    animation: sparkleAppear 0.5s ease-out forwards;
    pointer-events: none;
}

/* Stone Float Animation */
@keyframes stoneFloat {
    0%, 100% { transform: translate(-50%, -50%) translateY(0); }
    50% { transform: translate(-50%, -50%) translateY(-2px); }
}

/* Stone Pulse Animation */
@keyframes stonePulse {
    0%, 100% { 
        filter: brightness(1);
    }
    50% { 
        filter: brightness(1.2);
    }
}

/* Trail Pulse */
@keyframes trailPulse {
    0%, 100% { 
        transform: translate(-50%, -50%) scale(1);
        opacity: 0.5;
    }
    50% { 
        transform: translate(-50%, -50%) scale(1.3);
        opacity: 0.2;
    }
}

/* Sparkle Animation */
@keyframes sparkleAppear {
    0% { opacity: 0; transform: translate(-50%, -50%) scale(0.5) rotate(0deg); }
    50% { opacity: 1; }
    100% { opacity: 0; transform: translate(-50%, -50%) scale(1.5) rotate(180deg); }
}

/* ===== INFINITY STONE COLORS BY SECTION ===== */

/* Power Stone - Purple (Default / Hero Section) */
.hero-section .infinity-cursor,
.hero-section ~ .infinity-cursor {
    background: radial-gradient(circle at 30% 30%, 
        rgba(255, 255, 255, 0.9) 0%, 
        rgba(220, 180, 255, 1) 20%, 
        rgba(138, 43, 226, 1) 50%, 
        rgba(75, 0, 130, 0.9) 100%);
    box-shadow: 
        0 0 15px rgba(138, 43, 226, 0.9),
        0 0 30px rgba(138, 43, 226, 0.7),
        0 0 45px rgba(138, 43, 226, 0.5),
        inset 0 0 10px rgba(255, 255, 255, 0.4);
}

/* Space Stone - Blue (Home Section) */
.infinity-cursor.stone-space {
    background: radial-gradient(circle at 30% 30%, 
        rgba(255, 255, 255, 0.9) 0%, 
        rgba(100, 180, 255, 1) 20%, 
        rgba(30, 144, 255, 1) 50%, 
        rgba(0, 50, 150, 0.9) 100%);
    box-shadow: 
        0 0 15px rgba(30, 144, 255, 0.9),
        0 0 30px rgba(30, 144, 255, 0.7),
        0 0 45px rgba(30, 144, 255, 0.5),
        inset 0 0 10px rgba(255, 255, 255, 0.4);
}

.infinity-cursor.stone-space::before {
    background: radial-gradient(circle, rgba(30, 144, 255, 0.3) 0%, transparent 70%);
}

/* Mind Stone - Yellow (About Section) */
.infinity-cursor.stone-mind {
    background: radial-gradient(circle at 30% 30%, 
        rgba(255, 255, 255, 0.95) 0%, 
        rgba(255, 255, 150, 1) 20%, 
        rgba(255, 215, 0, 1) 50%, 
        rgba(200, 150, 0, 0.9) 100%);
    box-shadow: 
        0 0 15px rgba(255, 215, 0, 0.9),
        0 0 30px rgba(255, 215, 0, 0.7),
        0 0 45px rgba(255, 215, 0, 0.5),
        inset 0 0 10px rgba(255, 255, 255, 0.5);
}

.infinity-cursor.stone-mind::before {
    background: radial-gradient(circle, rgba(255, 215, 0, 0.3) 0%, transparent 70%);
}

/* Reality Stone - Red (Cast Section) */
.infinity-cursor.stone-reality {
    background: radial-gradient(circle at 30% 30%, 
        rgba(255, 255, 255, 0.9) 0%, 
        rgba(255, 150, 150, 1) 20%, 
        rgba(220, 20, 60, 1) 50%, 
        rgba(139, 0, 0, 0.9) 100%);
    box-shadow: 
        0 0 15px rgba(220, 20, 60, 0.9),
        0 0 30px rgba(220, 20, 60, 0.7),
        0 0 45px rgba(220, 20, 60, 0.5),
        inset 0 0 10px rgba(255, 255, 255, 0.4);
}

.infinity-cursor.stone-reality::before {
    background: radial-gradient(circle, rgba(220, 20, 60, 0.3) 0%, transparent 70%);
}

/* Time Stone - Green (Gallery Section) */
.infinity-cursor.stone-time {
    background: radial-gradient(circle at 30% 30%, 
        rgba(255, 255, 255, 0.9) 0%, 
        rgba(150, 255, 150, 1) 20%, 
        rgba(50, 205, 50, 1) 50%, 
        rgba(0, 100, 0, 0.9) 100%);
    box-shadow: 
        0 0 15px rgba(50, 205, 50, 0.9),
        0 0 30px rgba(50, 205, 50, 0.7),
        0 0 45px rgba(50, 205, 50, 0.5),
        inset 0 0 10px rgba(255, 255, 255, 0.4);
}

.infinity-cursor.stone-time::before {
    background: radial-gradient(circle, rgba(50, 205, 50, 0.3) 0%, transparent 70%);
}

/* Soul Stone - Orange (Reviews Section) */
.infinity-cursor.stone-soul {
    background: radial-gradient(circle at 30% 30%, 
        rgba(255, 255, 255, 0.9) 0%, 
        rgba(255, 200, 150, 1) 20%, 
        rgba(255, 140, 0, 1) 50%, 
        rgba(180, 80, 0, 0.9) 100%);
    box-shadow: 
        0 0 15px rgba(255, 140, 0, 0.9),
        0 0 30px rgba(255, 140, 0, 0.7),
        0 0 45px rgba(255, 140, 0, 0.5),
        inset 0 0 10px rgba(255, 255, 255, 0.4);
}

.infinity-cursor.stone-soul::before {
    background: radial-gradient(circle, rgba(255, 140, 0, 0.3) 0%, transparent 70%);
}

/* ===== HOVER STATES - Stone Pulse Effect ===== */
.infinity-cursor.hover {
    width: 28px;
    height: 28px;
    animation: stoneFloat 2s ease-in-out infinite, hoverPulse 0.4s ease-out;
}

@keyframes hoverPulse {
    0% { transform: translate(-50%, -50%) scale(1); }
    50% { transform: translate(-50%, -50%) scale(1.4); }
    100% { transform: translate(-50%, -50%) scale(1); }
}

/* ===== CLICK STATE - Stone Burst ===== */
.infinity-cursor.click {
    animation: stoneBurst 0.3s ease-out;
}

@keyframes stoneBurst {
    0% { 
        transform: translate(-50%, -50%) scale(1);
        filter: brightness(1);
    }
    50% { 
        transform: translate(-50%, -50%) scale(1.8);
        filter: brightness(2);
    }
    100% { 
        transform: translate(-50%, -50%) scale(1);
        filter: brightness(1);
    }
}

/* ===== CURSOR TRAIL PARTICLES ===== */
.cursor-particle {
    position: fixed;
    width: 6px;
    height: 6px;
    border-radius: 50%;
    pointer-events: none;
    z-index: 99998;
    animation: particleFade 0.6s ease-out forwards;
}

@keyframes particleFade {
    0% {
        opacity: 1;
        transform: scale(1);
    }
    100% {
        opacity: 0;
        transform: scale(0);
    }
}

/* Particle colors matching stones */
.cursor-particle.power { background: rgba(138, 43, 226, 0.8); box-shadow: 0 0 8px rgba(138, 43, 226, 0.6); }
.cursor-particle.space { background: rgba(30, 144, 255, 0.8); box-shadow: 0 0 8px rgba(30, 144, 255, 0.6); }
.cursor-particle.mind { background: rgba(255, 215, 0, 0.8); box-shadow: 0 0 8px rgba(255, 215, 0, 0.6); }
.cursor-particle.reality { background: rgba(220, 20, 60, 0.8); box-shadow: 0 0 8px rgba(220, 20, 60, 0.6); }
.cursor-particle.time { background: rgba(50, 205, 50, 0.8); box-shadow: 0 0 8px rgba(50, 205, 50, 0.6); }
.cursor-particle.soul { background: rgba(255, 140, 0, 0.8); box-shadow: 0 0 8px rgba(255, 140, 0, 0.6); }

/* ===== LOADING/TRANSITION STATE - All Stones Cycle ===== */
.infinity-cursor.loading {
    animation: stoneFloat 2s ease-in-out infinite, stoneCycle 3s linear infinite;
}

@keyframes stoneCycle {
    0%, 16.66% {
        background: radial-gradient(circle at 30% 30%, rgba(255,255,255,0.9) 0%, rgba(220,180,255,1) 20%, rgba(138,43,226,1) 50%, rgba(75,0,130,0.9) 100%);
        box-shadow: 0 0 20px rgba(138, 43, 226, 0.9), 0 0 40px rgba(138, 43, 226, 0.6);
    }
    16.67%, 33.32% {
        background: radial-gradient(circle at 30% 30%, rgba(255,255,255,0.9) 0%, rgba(100,180,255,1) 20%, rgba(30,144,255,1) 50%, rgba(0,50,150,0.9) 100%);
        box-shadow: 0 0 20px rgba(30, 144, 255, 0.9), 0 0 40px rgba(30, 144, 255, 0.6);
    }
    33.33%, 49.99% {
        background: radial-gradient(circle at 30% 30%, rgba(255,255,255,0.95) 0%, rgba(255,255,150,1) 20%, rgba(255,215,0,1) 50%, rgba(200,150,0,0.9) 100%);
        box-shadow: 0 0 20px rgba(255, 215, 0, 0.9), 0 0 40px rgba(255, 215, 0, 0.6);
    }
    50%, 66.65% {
        background: radial-gradient(circle at 30% 30%, rgba(255,255,255,0.9) 0%, rgba(255,150,150,1) 20%, rgba(220,20,60,1) 50%, rgba(139,0,0,0.9) 100%);
        box-shadow: 0 0 20px rgba(220, 20, 60, 0.9), 0 0 40px rgba(220, 20, 60, 0.6);
    }
    66.66%, 83.32% {
        background: radial-gradient(circle at 30% 30%, rgba(255,255,255,0.9) 0%, rgba(150,255,150,1) 20%, rgba(50,205,50,1) 50%, rgba(0,100,0,0.9) 100%);
        box-shadow: 0 0 20px rgba(50, 205, 50, 0.9), 0 0 40px rgba(50, 205, 50, 0.6);
    }
    83.33%, 100% {
        background: radial-gradient(circle at 30% 30%, rgba(255,255,255,0.9) 0%, rgba(255,200,150,1) 20%, rgba(255,140,0,1) 50%, rgba(180,80,0,0.9) 100%);
        box-shadow: 0 0 20px rgba(255, 140, 0, 0.9), 0 0 40px rgba(255, 140, 0, 0.6);
    }
}

/* =========================================
   RESPONSIVE STYLES (Mobile & Tablet)
   ========================================= */

@media (max-width: 768px) {
    /* --- Global Layout Adjustments --- */
    
    /* Hide side images on mobile to prevent layout issues */
    .home-side-image,
    .section-side-image {
        display: none !important;
    }

    /* Adjust Home Content container */
    .home-content {
        padding: 10px;
        width: 100%;
        overflow-x: hidden;
    }

    /* Reset Rectangle Dimensions & Positioning */
    .home-rectangle,
    .home-rectangle.right {
        width: 95%;
        height: auto;
        min-height: 85vh;
        left: 0;
        margin: 0 auto;
        display: flex;
        flex-direction: column;
    }

    /* Adjust Image Wrapper inside Rectangle */
    .rectangle-image-wrapper {
        position: relative;
        width: 100%;
        height: 250px; /* Fixed height for image/video area on mobile */
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        margin-bottom: 0;
    }

    /* --- Navigation Adjustments --- */
    
    .rectangle-nav {
        position: relative; /* Stack normally in flow */
        flex-direction: column;
        padding: 10px;
        background: rgba(0, 0, 0, 0.9);
        height: auto;
    }

    .nav-logo-item {
        position: static; /* Reset positioning */
        margin-bottom: 10px;
        top: 0;
        left: 0;
    }

    .nav-links {
        flex-wrap: wrap;
        justify-content: center;
        gap: 15px;
        width: 100%;
    }

    .nav-link {
        position: static; /* Reset positioning */
        font-size: 1rem;
        top: 0;
        left: 0;
    }

    .nav-text {
        font-size: 1rem;
    }

    /* MVS Logo Corner - Adjust position */
    .about-mvs-corner {
        top: 10px;
        left: 10px;
        z-index: 100;
    }

    /* --- Section Specific Adjustments --- */

    /* Hero Section */
    .logo-image {
        width: 90%;
        max-width: 300px;
    }

    .enter-btn {
        padding: 10px 25px;
        font-size: 0.9rem;
    }

    /* Content Areas */
    .rectangle-content {
        position: relative;
        width: 100%;
        height: auto;
        padding: 20px;
        top: 0;
        left: 0;
        transform: none;
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
    }

    /* About Section */
    .about-content {
        flex-direction: column;
    }

    /* Cast Section - Detail View */
    .character-detail-view {
        flex-direction: column-reverse;
        margin-right: 0;
        padding: 10px;
    }

    .character-info-panel {
        width: 100%;
        padding: 10px;
        transform: none;
        opacity: 1;
        margin-top: 0;
    }

    .horizontal-3d-carousel {
        width: 100%;
        height: 300px;
        padding-right: 0;
        top: 0;
        transform: none;
        opacity: 1;
        justify-content: center;
    }

    .h3d-stage {
        width: 100%;
        height: 100%;
    }

    .char-name-preview, 
    .movie-preview {
        display: none !important;
    }

    /* Gallery Section */
    .gallery-content {
        flex-direction: column !important;
        padding: 20px !important;
        align-items: center !important;
    }

    .gallery-header {
        margin-left: 0;
        margin-top: 0;
        margin-bottom: 20px;
        flex-direction: row;
        height: auto;
        width: 100%;
        justify-content: center;
    }

    .gallery-title {
        writing-mode: horizontal-tb;
        transform: none;
        font-size: 2rem;
    }

    .gallery-line {
        width: 100px;
        height: 2px;
    }

    .gallery-carousel {
        padding-top: 0;
        width: 100%;
        align-items: center;
    }

    .gallery-slides {
        margin-right: 0;
        flex-wrap: wrap;
        justify-content: center;
    }

    .gallery-item.main-item {
        width: 100%;
        max-width: 250px;
        height: auto;
        aspect-ratio: 3/4;
    }

    .gallery-item.side-item {
        display: none; /* Hide side items on mobile to simplify */
    }

    .gallery-nav {
        justify-content: center;
        margin-top: 20px;
        padding-right: 0;
    }

    /* Reviews Section */
    .reviews-content {
        align-items: center !important;
        padding: 20px !important;
        text-align: center !important;
    }

    .reviews-panel {
        margin-right: 0;
        align-items: center;
        text-align: center;
    }

    .genre-tags {
        justify-content: center;
        flex-wrap: wrap;
    }

    .rating-section {
        justify-content: center;
    }

    .rating-info {
        align-items: center;
    }

    .review-side-btn {
        display: none;
    }
    
    .reviews-nav {
        justify-content: center;
    }

    /* Modal */
    .modal-content {
        width: 95%;
        margin: 10px;
        max-height: 90vh;
    }
    
    .modal-body {
        flex-direction: column;
        padding: 15px;
    }
    
    .modal-poster {
        width: 140px;
        margin: 0 auto 15px;
    }
}

const canvas = document.getElementById("pong");
const ctx = canvas.getContext("2d");

// Game settings
const paddleWidth = 12;
const paddleHeight = 100;
const paddleMargin = 10;
const ballRadius = 10;

const player = {
    x: paddleMargin,
    y: canvas.height/2 - paddleHeight/2,
    width: paddleWidth,
    height: paddleHeight,
    color: "#fff",
    score: 0
};

const ai = {
    x: canvas.width - paddleMargin - paddleWidth,
    y: canvas.height/2 - paddleHeight/2,
    width: paddleWidth,
    height: paddleHeight,
    color: "#fff",
    score: 0
};

const ball = {
    x: canvas.width/2,
    y: canvas.height/2,
    radius: ballRadius,
    speed: 6,
    velocityX: 6 * (Math.random() < 0.5 ? 1 : -1),
    velocityY: 6 * (Math.random() * 2 - 1),
    color: "#fff"
};

// Draw functions
function drawRect(x, y, w, h, color) {
    ctx.fillStyle = color;
    ctx.fillRect(x, y, w, h);
}

function drawCircle(x, y, r, color) {
    ctx.fillStyle = color;
    ctx.beginPath();
    ctx.arc(x, y, r, 0, Math.PI*2, false);
    ctx.closePath();
    ctx.fill();
}

function drawNet() {
    for (let i = 0; i < canvas.height; i += 30) {
        drawRect(canvas.width/2 - 1, i, 2, 20, "#aaa");
    }
}

function draw() {
    // Clear canvas
    drawRect(0, 0, canvas.width, canvas.height, "#000");

    drawNet();

    // Draw paddles
    drawRect(player.x, player.y, player.width, player.height, player.color);
    drawRect(ai.x, ai.y, ai.width, ai.height, ai.color);

    // Draw ball
    drawCircle(ball.x, ball.y, ball.radius, ball.color);

    // Draw scores
    ctx.font = "40px Arial";
    ctx.fillText(player.score, canvas.width/4, 50);
    ctx.fillText(ai.score, 3*canvas.width/4, 50);
}

// Mouse control for player paddle
canvas.addEventListener("mousemove", (evt) => {
    const rect = canvas.getBoundingClientRect();
    const mouseY = evt.clientY - rect.top;
    player.y = mouseY - player.height/2;

    // Prevent paddle from going out of bounds
    if (player.y < 0) player.y = 0;
    if (player.y + player.height > canvas.height) player.y = canvas.height - player.height;
});

// Collision Detection
function collision(b, p) {
    return (
        b.x - b.radius < p.x + p.width &&
        b.x + b.radius > p.x &&
        b.y - b.radius < p.y + p.height &&
        b.y + b.radius > p.y
    );
}

// Reset ball
function resetBall() {
    ball.x = canvas.width/2;
    ball.y = canvas.height/2;
    ball.speed = 6;
    ball.velocityX = ball.velocityX < 0 ? 6 : -6;
    ball.velocityY = 6 * (Math.random() * 2 - 1);
}

// Update game state
function update() {
    // Move ball
    ball.x += ball.velocityX;
    ball.y += ball.velocityY;

    // Top/bottom wall collision
    if (ball.y - ball.radius < 0 || ball.y + ball.radius > canvas.height) {
        ball.velocityY = -ball.velocityY;
    }

    // Player paddle collision
    if (collision(ball, player)) {
        ball.x = player.x + player.width + ball.radius;
        ball.velocityX = -ball.velocityX;
        // Add effect based on where it hits the paddle
        let collidePoint = ball.y - (player.y + player.height/2);
        collidePoint = collidePoint / (player.height/2);
        let angleRad = (Math.PI/4) * collidePoint;
        ball.velocityY = ball.speed * Math.sin(angleRad);
        ball.velocityX = ball.speed * Math.cos(angleRad);
        ball.speed += 0.2;
    }

    // AI paddle collision
    if (collision(ball, ai)) {
        ball.x = ai.x - ball.radius;
        ball.velocityX = -ball.velocityX;
        // Add effect based on where it hits the paddle
        let collidePoint = ball.y - (ai.y + ai.height/2);
        collidePoint = collidePoint / (ai.height/2);
        let angleRad = (Math.PI/4) * collidePoint;
        ball.velocityY = ball.speed * Math.sin(angleRad);
        ball.velocityX = -ball.speed * Math.cos(angleRad);
        ball.speed += 0.2;
    }

    // Score update
    if (ball.x - ball.radius < 0) {
        ai.score++;
        resetBall();
    } else if (ball.x + ball.radius > canvas.width) {
        player.score++;
        resetBall();
    }

    // Basic AI movement (follows ball with a bit of lag)
    let target = ball.y - (ai.height/2);
    ai.y += (target - ai.y) * 0.08;
    // Prevent AI paddle from going out of bounds
    if (ai.y < 0) ai.y = 0;
    if (ai.y + ai.height > canvas.height) ai.y = canvas.height - ai.height;
}

// Game loop
function gameLoop() {
    update();
    draw();
    requestAnimationFrame(gameLoop);
}

gameLoop();
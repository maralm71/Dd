# Dd
<!DOCTYPE html>
<html lang="fa">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تست دوربین</title>
</head>
<body>
    <h2>آیا دوربین کار می‌کند؟</h2>
    <video id="video" autoplay></video>
    <p id="status">منتظر دسترسی به دوربین...</p>

    <script>
        async function testCamera() {
            try {
                let stream = await navigator.mediaDevices.getUserMedia({ video: true });
                document.getElementById('video').srcObject = stream;
                document.getElementById('status').innerText = "✅ دوربین فعال شد!";
                console.log("✅ دوربین کار می‌کند.");
            } catch (error) {
                console.error("🚨 خطا در دسترسی به دوربین:", error);
                document.getElementById('status').innerText = "🚨 امکان دسترسی به دوربین وجود ندارد!";
            }
        }

        testCamera();
    </script>
</body>
</html>

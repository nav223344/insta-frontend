<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Instagram Downloader + Earn</title>
</head>
<body>
<h2>🎥 Instagram Downloader + Earn Tool</h2>

<input type="text" id="url" placeholder="Paste Instagram reel link" style="width:80%; padding:8px">
<button onclick="download()" style="padding:8px 16px;">Download Now</button>

<div id="result" style="margin-top:20px;"></div>

<hr>
<h3>💰 Sponsored Links / Affiliate Offers</h3>
<a href="https://amzn.to/YOUR_ID" target="_blank">🛍️ Amazon Best Deals</a><br>
<a href="https://affiliate-link.com" target="_blank">💸 Affiliate Signup (Free)</a><br>
<a href="https://t.me/yourchannel" target="_blank">📲 Join Telegram Deals Channel</a><br>
<div>👁️ Total Visitors: <span id="visitors">0</span></div>

<script>
const backend = "https://insta-backend-neah.onrender.com"; // Replace with your Render backend

async function download() {
  const link = document.getElementById('url').value.trim();
  if(!link){ alert("कृपया Instagram लिंक डालें"); return; }
  document.getElementById('result').innerHTML = "⏳ Fetching...";

  try{
    const api = `${backend}/api/download?url=${encodeURIComponent(link)}`;
    const res = await fetch(api);
    const j = await res.json();

    if(!j.ok){
      document.getElementById('result').innerHTML = `<div style="color:red">❌ Error: ${j.error || 'Unknown'}</div>`;
      return;
    }

    const media = j.download_url;
    document.getElementById('result').innerHTML = `
      <video controls style="width:95%;max-width:600px;border-radius:8px;margin-top:10px" src="${media}"></video>
      <div style="margin-top:8px">
        <a href="${media}" download target="_blank" style="display:inline-block;padding:10px 16px;background:#007bff;color:white;border-radius:6px;text-decoration:none">⬇️ Save Video</a>
      </div>
    `;
  } catch(err){
    document.getElementById('result').innerHTML = `<div style="color:red">❌ Network error</div>`;
  }
}
</script>
</body>
</html>

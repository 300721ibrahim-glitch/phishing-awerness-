<form id="form">
  <input id="name" placeholder="Your Name" required>
  <input id="email" type="email" placeholder="Your Email" required>
  <textarea id="message" placeholder="Message"></textarea>
  <button type="submit">Send</button>
</form>

<script>
const API = "YOUR_SCRIPT_URL_HERE"; // paste your Google script link

document.getElementById('form').addEventListener('submit', async (e)=>{
  e.preventDefault();

  const name = document.getElementById('name').value;
  const email = document.getElementById('email').value;
  const message = document.getElementById('message').value;

  const res = await fetch(API, {
    method: "POST",
    body: JSON.stringify({ name, email, message })
  });

  alert("Saved!");
});
</script>

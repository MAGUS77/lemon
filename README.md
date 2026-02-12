<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Lemon Feedback</title>
<style>
  /* Reset y tipografía */
  * {margin:0;padding:0;box-sizing:border-box;font-family:'Roboto',sans-serif;}
  body {background:#fffbe6;color:#333;display:flex;flex-direction:column;align-items:center;min-height:100vh;}
  header {padding:30px 20px;text-align:center;}
  header h1 {color:#f4c542;font-size:2.2rem;}
  header p {color:#333;font-size:1.2rem;margin-top:10px;}
  main {background:#fff;padding:30px;border-radius:15px;box-shadow:0 8px 20px rgba(0,0,0,0.1);width:90%;max-width:500px;margin-bottom:40px;}
  form {display:flex;flex-direction:column;gap:15px;}
  input, textarea {padding:12px;border-radius:8px;border:1px solid #ccc;font-size:1rem;width:100%;}
  textarea {resize:none;}
  .stars {display:flex;justify-content:space-between;max-width:220px;margin:0 auto;}
  .star {font-size:2rem;cursor:pointer;color:#ccc;transition:0.3s;}
  .star.selected, .star:hover, .star:hover ~ .star {color:#f4c542;}
  button {padding:15px;background:#f4c542;border:none;border-radius:10px;font-size:1.2rem;cursor:pointer;transition:0.3s;}
  button:hover {background:#e0b636;}
  .message {text-align:center;margin-top:20px;font-size:1.1rem;}
  a.google-link {color:#0f9d58;text-decoration:none;font-weight:bold;}
</style>
</head>
<body>

<header>
  <h1>Lemon</h1>
  <p>Gracias por tu visita. Cuéntanos cómo fue tu experiencia.</p>
</header>

<main>
  <form id="feedbackForm" action="https://formsubmit.co/TU_EMAIL" method="POST">
    <!-- Campos básicos -->
    <input type="text" name="nombre" placeholder="Nombre" required>
    <input type="text" name="apellido" placeholder="Apellido" required>

    <!-- Selección de estrellas -->
    <div class="stars" id="starRating">
      <span class="star" data-value="1">&#9733;</span>
      <span class="star" data-value="2">&#9733;</span>
      <span class="star" data-value="3">&#9733;</span>
      <span class="star" data-value="4">&#9733;</span>
      <span class="star" data-value="5">&#9733;</span>
    </div>

    <!-- Comentario opcional -->
    <textarea name="comentario" placeholder="Comentario (opcional)"></textarea>

    <!-- Campo oculto para rating -->
    <input type="hidden" name="rating" id="ratingHidden">

    <button type="submit">Enviar valoración</button>
  </form>

  <div class="message" id="message"></div>
</main>

<script>
  // Selección de estrellas
  const stars = document.querySelectorAll('.star');
  let rating = 0;
  const ratingHidden = document.getElementById('ratingHidden');
  stars.forEach(star => {
    star.addEventListener('click', () => {
      rating = star.getAttribute('data-value');
      ratingHidden.value = rating;
      stars.forEach(s => s.classList.remove('selected'));
      star.classList.add('selected');
      let prev = star.previousElementSibling;
      while(prev){prev.classList.add('selected'); prev=prev.previousElementSibling;}
    });
  });

  // Mensaje tras enviar
  const form = document.getElementById('feedbackForm');
  const messageDiv = document.getElementById('message');
  form.addEventListener('submit', e => {
    // No prevenir el submit porque Formsubmit maneja el envío
    setTimeout(() => {
      if(rating <= 3){
        messageDiv.innerText = 'Gracias por tu opinión. La clínica revisará tu feedback para mejorar.';
      } else {
        messageDiv.innerHTML = '¡Gracias! Ahora deja tu reseña en Google: <a class="google-link" href="<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Lemon Feedback</title>
<style>
  /* Reset y tipografía */
  * {margin:0;padding:0;box-sizing:border-box;font-family:'Roboto',sans-serif;}
  body {background:#fffbe6;color:#333;display:flex;flex-direction:column;align-items:center;min-height:100vh;}
  header {padding:30px 20px;text-align:center;}
  header h1 {color:#f4c542;font-size:2.2rem;}
  header p {color:#333;font-size:1.2rem;margin-top:10px;}
  main {background:#fff;padding:30px;border-radius:15px;box-shadow:0 8px 20px rgba(0,0,0,0.1);width:90%;max-width:500px;margin-bottom:40px;}
  form {display:flex;flex-direction:column;gap:15px;}
  input, textarea {padding:12px;border-radius:8px;border:1px solid #ccc;font-size:1rem;width:100%;}
  textarea {resize:none;}
  .stars {display:flex;justify-content:space-between;max-width:220px;margin:0 auto;}
  .star {font-size:2rem;cursor:pointer;color:#ccc;transition:0.3s;}
  .star.selected, .star:hover, .star:hover ~ .star {color:#f4c542;}
  button {padding:15px;background:#f4c542;border:none;border-radius:10px;font-size:1.2rem;cursor:pointer;transition:0.3s;}
  button:hover {background:#e0b636;}
  .message {text-align:center;margin-top:20px;font-size:1.1rem;}
  a.google-link {color:#0f9d58;text-decoration:none;font-weight:bold;}
</style>
</head>
<body>

<header>
  <h1>Lemon</h1>
  <p>Gracias por tu visita. Cuéntanos cómo fue tu experiencia.</p>
</header>

<main>
  <form id="feedbackForm" action="https://formsubmit.co/pedrodelmonte235@gmail.com" method="POST">
    <!-- Campos básicos -->
    <input type="text" name="nombre" placeholder="Nombre" required>
    <input type="text" name="apellido" placeholder="Apellido" required>

    <!-- Selección de estrellas -->
    <div class="stars" id="starRating">
      <span class="star" data-value="1">&#9733;</span>
      <span class="star" data-value="2">&#9733;</span>
      <span class="star" data-value="3">&#9733;</span>
      <span class="star" data-value="4">&#9733;</span>
      <span class="star" data-value="5">&#9733;</span>
    </div>

    <!-- Comentario opcional -->
    <textarea name="comentario" placeholder="Comentario (opcional)"></textarea>

    <!-- Campo oculto para rating -->
    <input type="hidden" name="rating" id="ratingHidden">

    <button type="submit">Enviar valoración</button>
  </form>

  <div class="message" id="message"></div>
</main>

<script>
  // Selección de estrellas
  const stars = document.querySelectorAll('.star');
  let rating = 0;
  const ratingHidden = document.getElementById('ratingHidden');
  stars.forEach(star => {
    star.addEventListener('click', () => {
      rating = star.getAttribute('data-value');
      ratingHidden.value = rating;
      stars.forEach(s => s.classList.remove('selected'));
      star.classList.add('selected');
      let prev = star.previousElementSibling;
      while(prev){prev.classList.add('selected'); prev=prev.previousElementSibling;}
    });
  });

  // Mensaje tras enviar
  const form = document.getElementById('feedbackForm');
  const messageDiv = document.getElementById('message');
  form.addEventListener('submit', e => {
    // No prevenir el submit porque Formsubmit maneja el envío
    setTimeout(() => {
      if(rating <= 3){
        messageDiv.innerText = 'Gracias por tu opinión. La clínica revisará tu feedback para mejorar.';
      } else {
        messageDiv.innerHTML = '¡Gracias! Ahora deja tu reseña en Google: <a class="google-link" href="[TU_LINK_GOOGLE_REVIEW](https://www.google.com/search?sca_esv=5fb6f69dac5a6c69&q=Cuchiller%C3%ADa+G%C3%B3mez+Rese%C3%B1as&rflfq=1&num=20&stick=H4sIAAAAAAAAAONgkxIxNDQwMjQwNzA1tjQ3tDQ2MjY0tdjAyPiKUca5NDkjMycntejw2kQF98Obc1OrFIJSi1MPb0wsXsSKVxoACSDxR1kAAAA&rldimm=11021070539719323158&tbm=lcl&hl=es-ES&sa=X&ved=2ahUKEwjYgP2sqdSSAxUTAfsDHSpoN9kQ9fQKegQIRBAG&biw=1920&bih=945&dpr=1#lkt=LocalPoiReviews&lrd=0xd5092fbfcd0a911:0x98f2b543847e2e16,3,,,,)" target="_blank">Click aquí</a>';
      }
      form.reset();
      rating = 0;
      stars.forEach(s => s.classList.remove('selected'));
    }, 500);
  });
</script>

</body>
</html>
" target="_blank">Click aquí</a>';
      }
      form.reset();
      rating = 0;
      stars.forEach(s => s.classList.remove('selected'));
    }, 500);
  });
</script>

</body>
</html>

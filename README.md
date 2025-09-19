# WEEK-2-WEB-DEV-ASSIGMENT-PLP
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>Enhanced Form — accessible HTML5 example</title>
  <meta name="description" content="An accessible HTML5 form demonstrating inputs, validation, semantic structure, lists, tables and embedded media.">
  <style>
    :root{--max-width:900px;--gap:1rem;font-family:system-ui,Segoe UI,Roboto,Arial}
    body{font-family:var(--font-family, system-ui);line-height:1.4;padding:1.5rem;background:#fbfbfb}
    main{max-width:var(--max-width);margin:0 auto;background:#fff;padding:1.5rem;border-radius:8px;box-shadow:0 6px 18px rgba(0,0,0,.06)}
    header h1{margin:.2rem 0}
    .grid{display:grid;grid-template-columns:1fr 320px;gap:var(--gap)}
    @media (max-width:900px){.grid{grid-template-columns:1fr}}
    label{display:block;font-weight:600;margin-bottom:.25rem}
    input,select,textarea{width:100%;padding:.5rem;border:1px solid #ccc;border-radius:6px}
    .row{display:flex;gap:.5rem}
    .note{font-size:.9rem;color:#555}
    .inline-help{font-size:.85rem;color:#666;margin-top:.25rem}
    .actions{display:flex;gap:.5rem;justify-content:flex-end;margin-top:1rem}
    .sr-only{position:absolute;width:1px;height:1px;padding:0;margin:-1px;overflow:hidden;clip:rect(0,0,0,0);white-space:nowrap;border:0}
    table{width:100%;border-collapse:collapse;margin-top:.5rem}
    th,td{padding:.5rem;border:1px solid #e6e6e6;text-align:left}
    .media{max-width:100%;height:auto;border-radius:6px}
    .error{color:#b00020;font-size:.9rem}
    .invalid{outline:2px solid #f8d7da}
  </style>
</head>
<body>
  <main>
    <header>
      <h1>Enhanced HTML5 Form</h1>
      <p class="note">This example demonstrates semantic structure, accessibility attributes, HTML5 validation and a variety of input types.</p>
    </header>

    <section class="grid">
      <section aria-labelledby="form-heading">
        <h2 id="form-heading">Registration & Preferences</h2>

        <form id="enhancedForm" action="#" method="post" novalidate>

          <fieldset>
            <legend>Personal information</legend>

            <label for="fullName">Full name</label>
            <input id="fullName" name="fullName" type="text" placeholder="Jane Example" autocomplete="name" required minlength="3">
            <div class="inline-help" id="nameHelp">Please enter your legal full name (3+ characters).</div>

            <label for="email">Email address</label>
            <input id="email" name="email" type="email" placeholder="name@example.com" autocomplete="email" required>
            <div class="inline-help" id="emailHelp">We'll use this to contact you.</div>

            <label for="phone">Phone (optional)</label>
            <input id="phone" name="phone" type="tel" placeholder="+254 7XX XXX XXX" autocomplete="tel" pattern="^\+?\d[\d\s-]{6,}$">

            <label for="bio">Short bio (readonly)</label>
            <textarea id="bio" name="bio" rows="3" readonly aria-readonly="true">This field is read-only for demonstration.</textarea>

          </fieldset>

          <fieldset>
            <legend>Account & security</legend>

            <label for="username">Username</label>
            <input id="username" name="username" type="text" placeholder="choose-a-username" autocomplete="username" minlength="4" maxlength="24" required>

            <label for="password">Password</label>
            <input id="password" name="password" type="password" placeholder="At least 8 characters" minlength="8" required aria-describedby="pwHelp">
            <div class="inline-help" id="pwHelp">Use 8+ characters with letters and numbers.</div>

            <label for="age">Age</label>
            <input id="age" name="age" type="number" min="13" max="120" required>

            <label for="website">Website (optional)</label>
            <input id="website" name="website" type="url" placeholder="https://example.com" autocomplete="url">

          </fieldset>

          <fieldset>
            <legend>Preferences</legend>

            <label for="productivity">Favorite productivity tool</label>
            <select id="productivity" name="productivity" required>
              <option value="">-- choose --</option>
              <option>Notes</option>
              <option>Calendar</option>
              <option>Task Manager</option>
              <option>Time Tracker</option>
            </select>

            <label>Notifications</label>
            <div class="row" role="group" aria-labelledby="notifLabel">
              <div>
                <input id="notifEmail" type="checkbox" name="notify" value="email">
                <label for="notifEmail">Email</label>
              </div>
              <div>
                <input id="notifSMS" type="checkbox" name="notify" value="sms">
                <label for="notifSMS">SMS</label>
              </div>
              <div>
                <input id="notifPush" type="checkbox" name="notify" value="push">
                <label for="notifPush">Push</label>
              </div>
            </div>

            <label for="color">Preferred UI color (readonly sample)</label>
            <input id="color" name="color" type="color" value="#1a73e8" readonly>

          </fieldset>

          <fieldset>
            <legend>Files & media</legend>
            <label for="avatar">Upload avatar (image)</label>
            <input id="avatar" name="avatar" type="file" accept="image/*">

            <label for="screenshot">Screenshot URL</label>
            <input id="screenshot" name="screenshot" type="url" placeholder="https://example.com/screenshot.png">

            <div class="inline-help">You can preview media in the panel on the right.</div>
          </fieldset>

          <div class="actions">
            <button type="reset">Reset</button>
            <button type="submit">Submit</button>
          </div>

        </form>

        <!-- A small table and list to satisfy the 'structured content' requirement -->
        <section aria-labelledby="info-heading">
          <h3 id="info-heading">Quick reference</h3>
          <p class="note">What this form demonstrates:</p>
          <ul>
            <li>Semantic grouping with <code>&lt;fieldset&gt;</code> and <code>&lt;legend&gt;</code></li>
            <li>Labels and accessible descriptions</li>
            <li>HTML5 validation attributes: <code>required</code>, <code>pattern</code>, <code>min</code>, <code>max</code>, <code>minlength</code></li>
          </ul>

          <table>
            <thead>
              <tr><th>Input</th><th>Purpose</th></tr>
            </thead>
            <tbody>
              <tr><td>email</td><td>Validated by type="email"</td></tr>
              <tr><td>age</td><td>Validated by min/max for numeric ranges</td></tr>
              <tr><td>username</td><td>Length constrained by minlength/maxlength</td></tr>
            </tbody>
          </table>
        </section>

      </section>

      <aside>
        <h3>Live preview</h3>
        <img id="previewImg" class="media" src="https://images.unsplash.com/photo-1517336714731-489689fd1ca8?fit=crop&w=800&q=60" alt="Laptop on a wooden desk">

        <h4>Productivity icons</h4>
        <img class="media" src="https://images.unsplash.com/photo-1518779578993-ec3579fee39f?fit=crop&w=800&q=60" alt="Icons for productivity tools">

        <h4>Form status</h4>
        <div id="status" aria-live="polite">Form not yet submitted.</div>

      </aside>
    </section>

    <footer>
      <p class="note">Hints: Use Tab/Shift+Tab to navigate, labels are programmatically associated with controls for screen readers.</p>
    </footer>

    <script>
      // Basic client-side validation glue that updates ARIA and shows messages
      (function(){
        const form = document.getElementById('enhancedForm');
        const status = document.getElementById('status');

        function setInvalid(el, message){
          el.classList.add('invalid');
          el.setAttribute('aria-invalid','true');
          let next = el.nextElementSibling;
          if(!next || !next.classList.contains('error')){
            const err = document.createElement('div');
            err.className = 'error';
            err.textContent = message;
            el.parentNode.insertBefore(err, el.nextSibling);
          } else {
            next.textContent = message;
          }
        }

        function clearInvalid(el){
          el.classList.remove('invalid');
          el.removeAttribute('aria-invalid');
          let next = el.nextElementSibling;
          if(next && next.classList.contains('error')) next.remove();
        }

        form.addEventListener('submit', function(e){
          // prevent default for demo — in real usage allow submission if valid
          e.preventDefault();
          // clear prior
          Array.from(form.elements).forEach(clearInvalid);
          let ok = true;

          // native check
          if(!form.checkValidity()){
            ok = false;
            // highlight invalid fields
            Array.from(form.elements).forEach(el => {
              if(typeof el.checkValidity === 'function' && !el.checkValidity()){
                const msg = el.validationMessage || 'Invalid value';
                setInvalid(el, msg);
              }
            });
          }

          if(ok){
            status.textContent = 'Form validated successfully — ready to submit.';
          } else {
            status.textContent = 'Please fix the highlighted fields.';
          }
        });

        // live validation on blur
        form.addEventListener('blur', function(e){
          const el = e.target;
          if(!el || !('checkValidity' in el)) return;
          if(el.checkValidity()) clearInvalid(el); else setInvalid(el, el.validationMessage || 'Invalid');
        }, true);

      })();
    </script>
  </main>
</body>
</html>

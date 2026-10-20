# A.Care
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>ACare</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <div class="app-shell">
    <aside class="sidebar">
      <div class="brand">
        <span class="brand-mark">✳</span>
        <span>ACare</span>
      </div>

      <nav class="nav">
        <button class="nav-button active" data-target="home">⌂ Home</button>
        <button class="nav-button" data-target="medications">✚ Medications</button>
        <button class="nav-button" data-target="visits">♡ Appointments</button>
        <button class="nav-button" data-target="notes">▤ Notes</button>
        <button class="nav-button" data-target="circle">☻ Care circle</button>
        <button class="nav-button" data-target="plans">◈ Plans</button>
      </nav>

      <div class="sidebar-note">
        <strong>🔒 Private demo</strong>
        <p>Sample data only. No live clinic, billing, or secure medical data is connected.</p>
      </div>
    </aside>

    <main class="main">
      <header class="topbar">
        <div>
          <div class="top-date" id="todayLabel"></div>
          <h1 id="greeting">Good day, Alex</h1>
        </div>

        <div class="toolbar">
          <select id="langSelect" aria-label="Language">
            <option value="en">English</option>
            <option value="zh">中文</option>
          </select>
          <button id="fontSmaller">A−</button>
          <button id="fontLarger">A+</button>
        </div>
      </header>

      <section id="home" class="page active">
        <div class="hero">
          <h2>Care that listens, in your language.</h2>
          <p>A calmer way to organize everyday care.</p>
        </div>

        <div class="content-grid">
          <div class="column">
            <div class="card">
              <div class="card-head">
                <div>
                  <h3>Talk with ACare</h3>
                  <p class="subtle">Tap to speak or choose a question.</p>
                </div>
                <span class="pill demo">SCRIPTED DEMO</span>
              </div>

              <div class="voice-box">
                <button id="micButton" class="mic-button">🎙</button>
                <div>
                  <strong>Tap to speak</strong>
                  <small>Microphone permission and browser support required.</small>
                </div>
              </div>

              <div id="heardText" class="heard"></div>
              <div id="assistantReply" class="assistant-reply"></div>

              <div class="chip-row">
                <button class="chip" data-prompt="meds">What is on my schedule?</button>
                <button class="chip" data-prompt="visits">What is coming up?</button>
                <button class="chip" data-prompt="explain">Explain a label simply</button>
                <button class="chip" data-prompt="repeat">Repeat</button>
              </div>

              <p class="tiny-note">Scripted preview only. AI advice and medical translation are not connected.</p>
            </div>

            <div class="card">
              <div class="card-head">
                <div>
                  <h3>Medication reminders</h3>
                  <p class="subtle">Fictional examples • confirm your own plan with your care team.</p>
                </div>
                <button class="secondary-btn" id="addMedicationBtn">＋ Add</button>
              </div>

              <div id="todayMeds"></div>
            </div>

            <div class="card">
              <div class="card-head">
                <div>
                  <h3>Upcoming care</h3>
                  <p class="subtle">Example visits and requests.</p>
                </div>
                <button class="link-btn" data-target="visits">View all →</button>
              </div>

              <div id="upcomingVisits"></div>
            </div>
          </div>

          <div class="column">
            <div class="card">
              <div class="card-head">
                <div>
                  <h3 id="calendarMonth"></h3>
                  <p class="subtle">Your appointments this month.</p>
                </div>
                <span class="pill" id="eventCount">0 events</span>
              </div>

              <div id="calendar" class="calendar"></div>
            </div>

            <div class="card">
              <div class="card-head">
                <div>
                  <h3>Refill reminders</h3>
                  <p class="subtle">Based on dates you enter • check with your pharmacy.</p>
                </div>
              </div>

              <div id="refillPreview"></div>
              <button class="secondary-btn wide-btn" data-target="medications">Review medication dates</button>
            </div>

            <div class="card">
              <h3>Gentle reminders</h3>
              <p class="subtle">Permission-based browser notifications.</p>
              <button class="secondary-btn" id="enableNotifications">Enable notifications</button>
              <p class="tiny-note">This demo does not schedule dependable reminders. Keep using your normal system.</p>
            </div>
          </div>
        </div>
      </section>

      <section id="medications" class="page">
        <div class="page-head">
          <div>
            <h2>Medications</h2>
            <p>Organize a schedule confirmed with your care team.</p>
          </div>
          <button class="primary-btn" id="openMedDialog">＋ Add medication</button>
        </div>

        <div class="content-grid">
          <div class="column">
            <div class="card">
              <div class="card-head">
                <div>
                  <h3>My schedule</h3>
                  <p class="subtle">Fictional examples. This demo does not verify prescriptions.</p>
                </div>
                <span class="pill" id="medCount">0 / 0</span>
              </div>

              <div id="medList"></div>
            </div>

            <div class="card">
              <div class="card-head">
                <div>
                  <h3>Refill tracking</h3>
                  <p class="subtle">Set your own reminder date.</p>
                </div>
              </div>

              <div id="refillList"></div>
            </div>
          </div>

          <div class="column">
            <div class="card">
              <div class="card-head">
                <div>
                  <h3>Medication label photo</h3>
                  <p class="subtle">Preview a photo locally; no text extraction or upload.</p>
                </div>
              </div>

              <label class="secondary-btn file-label" for="scanInput">📷 Choose photo</label>
              <input type="file" id="scanInput" accept="image/*" class="file-input" />

              <img id="imagePreview" class="image-preview" alt="Medication label preview" />
              <p class="tiny-note">Local image preview only • no text extraction or upload</p>
            </div>

            <div class="card">
              <h3>Safety</h3>
              <div class="alert-box">ACare is a prototype and not medical advice. Contact local emergency services for urgent concerns.</div>
            </div>
          </div>
        </div>
      </section>

      <section id="visits" class="page">
        <div class="page-head">
          <div>
            <h2>Appointments</h2>
            <p>Track demo requests. No clinic is connected.</p>
          </div>
          <button class="primary-btn" id="openVisitDialog">＋ Request appointment</button>
        </div>

        <div class="content-grid">
          <div class="column">
            <div class="card">
              <div class="card-head">
                <div>
                  <h3>Visits and requests</h3>
                  <p class="subtle">Requests stay in this preview.</p>
                </div>
              </div>
              <div id="visitList"></div>
            </div>
          </div>

          <div class="column">
            <div class="card">
              <h3>Reminder preview</h3>
              <div id="visitSummary" class="empty-state">No upcoming visits.</div>
            </div>
          </div>
        </div>
      </section>

      <section id="notes" class="page">
        <div class="page-head">
          <div>
            <h2>Health notes</h2>
            <p>Browser-only demo. Avoid entering real health information.</p>
          </div>
        </div>

        <div class="content-grid">
          <div class="column">
            <div class="card">
              <h3>Care note</h3>
              <form id="noteForm">
                <label class="label" for="noteInput">Your note</label>
                <textarea id="noteInput" rows="5" placeholder="A question for your next visit..."></textarea>
                <button type="submit" class="primary-btn">Save note</button>
              </form>
            </div>
          </div>

          <div class="column">
            <div class="card">
              <div class="card-head">
                <div>
                  <h3>Care notes</h3>
                  <p class="subtle">Notes stay in this browser only.</p>
                </div>
              </div>
              <div id="notesList"></div>
            </div>
          </div>
        </div>
      </section>

      <section id="circle" class="page">
        <div class="page-head">
          <div>
            <h2>Care circle</h2>
            <p>Trusted people and care tasks.</p>
          </div>
        </div>

        <div class="content-grid">
          <div class="column">
            <div class="card">
              <h3>Trusted people</h3>
              <form id="personForm">
                <label class="label" for="personNameInput">Name</label>
                <input id="personNameInput" type="text" />

                <label class="label" for="personContactInput">Contact detail (optional)</label>
                <input id="personContactInput" type="text" />

                <button type="submit" class="primary-btn">＋ Add person</button>
              </form>
            </div>
          </div>

          <div class="column">
            <div class="card">
              <div class="card-head">
                <div>
                  <h3>Care tasks to review</h3>
                  <p class="subtle">Shared schedules and caregiver notifications are not connected.</p>
                </div>
              </div>

              <div id="tasksList"></div>
            </div>

            <div class="card">
              <h3>Trusted people</h3>
              <div id="circleList"></div>
            </div>
          </div>
        </div>
      </section>

      <section id="plans" class="page">
        <div class="page-head">
          <div>
            <h2>Plans</h2>
            <p>Compare example plan limits. No payment is collected.</p>
          </div>
        </div>

        <div class="card">
          <div class="card-head">
            <div>
              <h3 id="planTitle">Free • Current</h3>
              <p class="subtle">Usage in this browser preview</p>
            </div>
          </div>

          <div id="usageStats" class="usage-block"></div>
        </div>

        <div id="plansGrid" class="plans-grid"></div>
      </section>
    </main>
  </div>

  <dialog id="medDialog">
    <form id="medForm" class="modal-form">
      <div class="dialog-head">
        <h3>Add medication schedule</h3>
        <button type="button" class="close-btn" data-close="medDialog">×</button>
      </div>

      <label class="label" for="medName">Medication name</label>
      <input id="medName" type="text" required />

      <label class="label" for="medDose">Directions as written</label>
      <input id="medDose" type="text" required />

      <div class="two-col">
        <div>
          <label class="label" for="medTime">Reminder time</label>
          <input id="medTime" type="time" value="08:00" required />
        </div>

        <div>
          <label class="label" for="medFreq">Frequency</label>
          <select id="medFreq">
            <option>Once daily</option>
            <option>Twice daily</option>
            <option>Every morning</option>
            <option>Every evening</option>
            <option>As directed</option>
          </select>
        </div>
      </div>

      <label class="label" for="medRefill">Optional refill reminder date</label>
      <input id="medRefill" type="date" />

      <div class="dialog-actions">
        <button type="button" class="secondary-btn" data-close="medDialog">Cancel</button>
        <button type="submit" class="primary-btn">Save schedule</button>
      </div>
    </form>
  </dialog>

  <dialog id="refillDialog">
    <form id="refillForm" class="modal-form">
      <div class="dialog-head">
        <h3>Set refill reminder</h3>
        <button type="button" class="close-btn" data-close="refillDialog">×</button>
      </div>

      <p id="refillMedicationName" class="subtle"></p>

      <label class="label" for="refillDate">Reminder date</label>
      <input id="refillDate" type="date" required />

      <div class="dialog-actions">
        <button type="button" class="secondary-btn" data-close="refillDialog">Cancel</button>
        <button type="submit" class="primary-btn">Save reminder</button>
      </div>
    </form>
  </dialog>

  <dialog id="visitDialog">
    <form id="visitForm" class="modal-form">
      <div class="dialog-head">
        <h3>Request appointment</h3>
        <button type="button" class="close-btn" data-close="visitDialog">×</button>
      </div>

      <label class="label" for="visitProvider">Provider or clinic</label>
      <input id="visitProvider" type="text" required />

      <label class="label" for="visitReason">Reason for visit</label>
      <input id="visitReason" type="text" required />

      <div class="two-col">
        <div>
          <label class="label" for="visitDate">Preferred date</label>
          <input id="visitDate" type="date" required />
        </div>

        <div>
          <label class="label" for="visitTime">Preferred time</label>
          <select id="visitTime">
            <option>Morning</option>
            <option>Afternoon</option>
            <option>Any time</option>
          </select>
        </div>
      </div>

      <label class="label" for="visitType">Visit type</label>
      <select id="visitType">
        <option>In person</option>
        <option>Video visit</option>
        <option>Phone call</option>
      </select>

      <div class="alert-box">Saved in demo only. No clinic is contacted or booked.</div>

      <div class="dialog-actions">
        <button type="button" class="secondary-btn" data-close="visitDialog">Cancel</button>
        <button type="submit" class="primary-btn">Save request</button>
      </div>
    </form>
  </dialog>

  <div id="toast" class="toast"></div>

  <script src="app.js"></script>
</body>
</html>

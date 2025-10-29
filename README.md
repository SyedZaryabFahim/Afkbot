<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>AFK Bot — Pookie Tech Team</title>
  <style>
    :root{
      --bg:#0f1724;
      --card:#0b1220;
      --muted:#94a3b8;
      --accent:#7c3aed;
      --glass: rgba(255,255,255,0.03);
      --white:#e6eef8;
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    html,body{height:100%;margin:0;background:linear-gradient(180deg,#071028 0%, #071b2d 100%);color:var(--white);}
    .wrap{max-width:900px;margin:36px auto;padding:28px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border-radius:12px;box-shadow:0 8px 30px rgba(2,6,23,0.6);border:1px solid rgba(255,255,255,0.03);}
    header{display:flex;align-items:center;gap:16px;margin-bottom:18px;}
    .logo{
      width:68px;height:68px;border-radius:12px;background:linear-gradient(135deg,var(--accent),#06b6d4);display:flex;align-items:center;justify-content:center;font-weight:700;color:white;font-size:20px;box-shadow:0 6px 20px rgba(124,58,237,0.18);
    }
    h1{margin:0;font-size:28px;letter-spacing:-0.2px;}
    p.lead{margin:6px 0 18px;color:var(--muted);max-width:78%;}
    section{margin-top:18px;}
    h2{font-size:18px;margin:14px 0 8px;color:var(--white);}
    ul{line-height:1.6;color:var(--muted);}
    pre{background:rgba(255,255,255,0.02);padding:12px;border-radius:8px;overflow:auto;color:var(--white);border:1px solid rgba(255,255,255,0.02);}
    code{font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, "Roboto Mono", "Courier New", monospace;font-size:13px;}
    .grid{display:grid;grid-template-columns:1fr 1fr;gap:12px;}
    .card{background:var(--card);padding:12px;border-radius:10px;border:1px solid rgba(255,255,255,0.02);}
    .btns{display:flex;gap:8px;margin-top:12px;flex-wrap:wrap;}
    .btn{
      display:inline-block;padding:8px 12px;border-radius:10px;background:linear-gradient(90deg,var(--accent),#06b6d4);color:white;text-decoration:none;font-weight:600;box-shadow:0 6px 18px rgba(2,6,23,0.35);
    }
    footer{margin-top:20px;color:var(--muted);font-size:13px;border-top:1px dashed rgba(255,255,255,0.03);padding-top:14px;display:flex;align-items:center;justify-content:space-between;gap:12px;}
    .credits{line-height:1.3;}
    @media (max-width:720px){
      .grid{grid-template-columns:1fr;}
      p.lead{max-width:100%;}
      header{gap:12px;}
    }
  </style>
</head>
<body>
  <div class="wrap" role="main">
    <header>
      <div class="logo">AFK</div>
      <div>
        <h1>AFK Bot</h1>
        <p class="lead">A lightweight Telegram bot to manage AFK (Away From Keyboard) statuses with fun reasons, admin controls, and automatic notifications.</p>
      </div>
    </header>

    <section>
      <h2>🌙 Features</h2>
      <ul>
        <li>Set yourself as AFK with a reason using <code>/afk [reason]</code> or <code>brb [reason]</code></li>
        <li>AFK status is automatically removed when you send a message again</li>
        <li>Notifies users who mention or reply to an AFK user</li>
        <li>Admins can toggle special AFK mode for users (AFK won’t break if a message starts with <code>!</code>) using <code>/safk</code> (reply)</li>
        <li><code>/help</code> and <code>/start</code> commands included</li>
      </ul>
    </section>

    <section>
      <h2>⚙️ Setup</h2>
      <div class="grid">
        <div class="card">
          <h3>1. Clone the repo</h3>
          <pre><code>git clone https://github.com/SyedZaryabFahim/Afkbot
cd Afkbot</code></pre>
        </div>

        <div class="card">
          <h3>2. Install dependencies</h3>
          <pre><code>pip install -r requirements.txt</code></pre>
        </div>

        <div class="card">
          <h3>3. Setup environment</h3>
          <pre><code>mv sample.env .env
# then open .env and fill your values</code></pre>
        </div>

        <div class="card">
          <h3>4. Example .env</h3>
          <pre><code>API_ID=your_api_id
API_HASH=your_api_hash
BOT_TOKEN=your_bot_token
ADMINS=123456789,987654321</code></pre>
        </div>
      </div>

      <p style="color:var(--muted);margin-top:12px;">Add AFK reasons in <code>funny_afk_reasons.txt</code> (one reason per line).</p>

      <h3 style="margin-top:12px;">Run</h3>
      <pre><code>python afk.py</code></pre>
    </section>

    <section>
      <h2>💬 Usage</h2>
      <ul>
        <li><code>/afk [reason]</code> — Set yourself as AFK</li>
        <li><code>brb [reason]</code> — Set yourself as AFK</li>
        <li><code>/safk</code> — Admins only, reply to a user to toggle special AFK mode</li>
        <li><code>/help</code> — Show help message</li>
        <li><code>/start</code> — Shows welcome message</li>
      </ul>
    </section>

    <section>
      <h2>📁 Files</h2>
      <ul>
        <li><code>afk.py</code> — Main bot script</li>
        <li><code>funny_afk_reasons.txt</code> — One reason per line for random AFK reasons</li>
        <li><code>sample.env</code> — Template environment variables (do not commit real <code>.env</code>)</li>
        <li><code>requirements.txt</code> — Dependency list</li>
        <li><code>afk_bot.db</code> — SQLite DB created at runtime</li>
        <li><code>afk_bot.log</code> — Log file (created at runtime)</li>
      </ul>
    </section>

    <section>
      <h2>🛡 Security Notes</h2>
      <ul>
        <li>Never commit real credentials to the repository. Keep a local <code>.env</code> and add it to <code>.gitignore</code>.</li>
        <li>If you accidentally push tokens, rotate them immediately (Bot token, API keys, DB credentials).</li>
        <li>Use <code>sample.env</code> to show required variables without leaking secrets.</li>
      </ul>
    </section>

    <section>
      <h2>🔧 Requirements</h2>
      <pre><code>telethon==1.34.0
python-dotenv==1.0.1</code></pre>
    </section>

    <section>
      <h2>📣 Credits</h2>
      <p class="credits">
        <strong>Made by:</strong> Pookie Tech Team<br />
        <strong>Developer:</strong> ZARYAB'<br />
        <strong>Channel:</strong> <a href="https://t.me/pookie_updates" target="_blank" rel="noopener" style="color:var(--accent);text-decoration:none;">@pookie_updates</a><br />
        <strong>Support:</strong> <a href="https://t.me/therichfamily" target="_blank" rel="noopener" style="color:var(--accent);text-decoration:none;">@therichfamily</a>
      </p>

      <div class="btns" aria-hidden="false">
        <a class="btn" href="https://github.com/SyedZaryabFahim/Afkbot" target="_blank" rel="noopener">View Repo</a>
        <a class="btn" href="https://t.me/pookie_updates" target="_blank" rel="noopener">Channel</a>
      </div>
    </section>

    <footer>
      <div style="font-size:13px;color:var(--muted);">AFK Bot • Lightweight Telegram AFK manager</div>
      <div style="font-size:13px;color:var(--muted);">Made with ❤️ by Pookie Tech Team</div>
    </footer>
  </div>
</body>
</html>
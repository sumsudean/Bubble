<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bubble AI - Pure HTML System</title>
    <style>
        :root {
            --bg-color: #0d1117;
            --panel-bg: #161b22;
            --primary-blue: #0070f3;
            --primary-green: #00df89;
            --text-light: #f0f6fc;
            --text-muted: #8b949e;
        }

        * { 
            box-sizing: border-box; 
            margin: 0; 
            padding: 0; 
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; 
        }
        
        body { 
            background-color: var(--bg-color); 
            color: var(--text-light); 
            display: flex; 
            height: 100vh; 
            overflow: hidden;
        }
        
        /* Layout Structure */
        .sidebar { 
            width: 320px; 
            background-color: var(--panel-bg); 
            border-right: 1px solid #30363d; 
            display: flex; 
            flex-direction: column; 
            padding: 20px; 
        }
        
        .main-content { 
            flex: 1; 
            position: relative;
            background: radial-gradient(circle at top right, rgba(0,223,137,0.03), transparent 40%), 
                        radial-gradient(circle at bottom left, rgba(0,112,243,0.03), transparent 40%); 
        }
        
        /* Branding Elements */
        h2 { 
            color: var(--primary-green); 
            margin-bottom: 20px; 
            font-size: 1.4rem; 
        }

        /* User Counter Badge */
        .user-counter {
            font-size: 0.85rem;
            color: var(--text-muted);
            margin-bottom: 20px;
            padding: 8px 12px;
            background: #21262d;
            border: 1px solid #30363d;
            border-radius: 6px;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .pulse-dot {
            width: 8px;
            height: 8px;
            background-color: var(--primary-green);
            border-radius: 50%;
            display: inline-block;
            box-shadow: 0 0 8px var(--primary-green);
        }
        
        /* Navigation Anchors */
        .nav-btn { 
            background: #21262d; 
            color: var(--text-light); 
            border: 1px solid #30363d; 
            padding: 12px; 
            border-radius: 6px; 
            margin-bottom: 10px; 
            text-align: left; 
            font-size: 0.9rem; 
            text-decoration: none;
            display: block;
            transition: 0.2s; 
        }
        .nav-btn:hover { 
            border-color: var(--primary-blue); 
            color: var(--primary-blue); 
        }
        
        /* Login Form Simulation */
        .login-box { 
            margin-top: auto; 
            padding: 15px; 
            background: #0d1117; 
            border-radius: 6px; 
            border: 1px solid #30363d; 
        }
        .login-box p { font-size: 0.8rem; color: var(--text-muted); margin-bottom: 8px; }
        
        input[type="text"], input[type="password"] { 
            width: 100%;
            background-color: #161b22; 
            border: 1px solid #30363d; 
            padding: 10px; 
            border-radius: 6px; 
            color: var(--text-light); 
            font-size: 0.9rem; 
            margin-bottom: 8px;
        }
        
        .action-btn { 
            width: 100%;
            background: linear-gradient(135deg, var(--primary-blue), #1f85ff); 
            color: white; 
            border: none; 
            padding: 10px; 
            border-radius: 6px; 
            font-weight: bold; 
            text-decoration: none;
            text-align: center;
            display: block;
        }
        
        /* Target-Based Pure HTML View Switcher */
        #chatView, #adminView {
            position: absolute;
            top: 0; left: 0; right: 0; bottom: 0;
            display: none;
            flex-direction: column;
            height: 10

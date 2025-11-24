<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CD11b/CD18 Integrin Activation Simulator</title>
    <style>
        :root {
            --membrane-color: #e0e0e0;
            --cytoplasm-color: #f9f9f9;
            --alpha-color: #3b82f6; /* CD11b Blue */
            --beta-color: #10b981;  /* CD18 Green */
            --ligand-color: #ef4444; /* ICAM-1/iC3b Red */
            --bg-color: #1e293b;
            --text-color: #f1f5f9;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            margin: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
        }

        header {
            text-align: center;
            padding: 20px;
            max-width: 800px;
        }

        h1 { margin: 0; font-size: 1.8rem; }
        p.subtitle { color: #94a3b8; font-size: 0.9rem; margin-top: 5px; }

        /* --- VISUALIZATION STAGE --- */
        #stage {
            position: relative;
            width: 800px;
            height: 400px;
            background: linear-gradient(to bottom, #0f172a 60%, var(--cytoplasm-color) 60%);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 10px 25px rgba(0,0,0,0.5);
            border: 1px solid #334155;
        }

        /* Membrane */
        .membrane {
            position: absolute;
            top: 60%;
            left: 0;
            width: 100%;
            height: 20px;
            background: repeating-linear-gradient(90deg, #cbd5e1 0px, #cbd5e1 10px, #94a3b8 10px, #94a3b8 12px);
            box-shadow: 0 0 10px rgba(0,0,0,0.2);
            z-index: 10;
        }
        
        .membrane-label {
            position: absolute;
            top: 62%;
            left: 10px;
            font-size: 0.8rem;
            color: #64748b;
            font-weight: bold;
        }

        /* --- INTEGRIN STRUCTURE (Schematic) --- */
        /* The container for the whole protein */
        #integrin {
            position: absolute;
            top: 60%; /* Anchored at membrane */
            left: 50%;
            transform: translate(-50%, -10px); /* Center anchor */
            width: 60px;
            height: 0; /* Height grows in animation */
            z-index: 20;
            transition: all 0.8s cubic-bezier(0.34, 1.56, 0.64, 1);
        }

        /* Common styles for subunits */
        .subunit {
            position: absolute;
            bottom: 0;
            border-radius: 20px;
            transition: all 0.8s ease;
            transform-origin: bottom center;
        }

        /* CD18 (Beta-2) - The "Leg" */
        .beta-subunit {
            width: 12px;
            height: 70px;
            background-color: var(--beta-color);
            left: 28px;
            transform: rotate(-45deg); /* Bent state */
            border: 2px solid #065f46;
        }
        
        /* CD11b (Alpha-M) - The "Head" and "Leg" */
        .alpha-subunit {
            width: 16px;
            height: 80px;
            background-color: var(--alpha-color);
            left: 14px;
            transform: rotate(45deg); /* Bent state */
            border: 2px solid #1e40af;
        }

        /* The Headpiece (Ligand Binding Domain / I-domain) */
        .headpiece {
            position: absolute;
            top: -20px;
            left: -8px;
            width: 36px;
            height: 25px;
            background-color: #60a5fa; /* Lighter blue for active site */
            border-radius: 50% 50% 10% 10%;
            border: 2px solid #1e40af;
            transform-origin: bottom center;
            transform: rotate(90deg) translateX(20px); /* Tucked in inactive */
            transition: all 0.8s ease;
        }

        /* Binding Pocket Indicator */
        .midas-site {
            position: absolute;
            top: 5px;
            left: 50%;
            transform: translateX(-50%);
            width: 8px;
            height: 8px;
            background-color: #fbbf24; /* Gold for Mg2+ ion */
            border-radius: 50%;
            opacity: 0.3;
            box-shadow: 0 0 5px #fbbf24;
            transition: opacity 0.5s;
        }

        /* --- LIGAND (ICAM-1 / iC3b) --- */
        #ligand {
            position: absolute;
            top: 50px;
            left: 80%; /* Start off-screen or far right */
            width: 40px;
            height: 40px;
            background-color: var(--ligand-color);
            clip-path: polygon(20% 0%, 80% 0%, 100% 100%, 0% 100%); /* Trapezoid */
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 0.7rem;
            font-weight: bold;
            transition: all 1.2s ease-in-out;
            opacity: 0.6;
        }

        /* --- ANIMATION STATES --- */

        /* State: ACTIVATED (Extended Open) */
        #integrin.active .alpha-subunit {
            transform: rotate(-10deg);
            height: 110px; /* Extension */
        }
        #integrin.active .beta-subunit {
            transform: rotate(10deg);
            height: 100px; /* Extension */
        }
        #integrin.active .headpiece {
            transform: rotate(0deg) translateX(0); /* Open head */
            top: -25px;
        }
        #integrin.active .midas-site {
            opacity: 1; /* Metal ion exposed */
        }

        /* State: LIGAND BOUND */
        #ligand.bound {
            top: 205px; /* Adjust based on extended height */
            left: 48%; /* Align with integrin head */
            opacity: 1;
            transform: scale(1.1);
        }

        /* State: PHAGOCYTOSIS / PULLING */
        #integrin.pulling {
            transform: translate(-50%, 20px); /* Sink into cell */
        }
        .membrane.pulling-effect {
            animation: ripple 1s infinite linear;
        }

        @keyframes ripple {
            0% { box-shadow: 0 -5px 10px rgba(0,0,0,0.1); }
            50% { box-shadow: 0 -15px 20px rgba(0,0,0,0.2); }
            100% { box-shadow: 0 -5px 10px rgba(0,0,0,0.1); }
        }

        /* --- CONTROLS --- */
        #controls {
            margin-top: 20px;
            display: flex;
            gap: 15px;
            background: #334155;
            padding: 15px;
            border-radius: 8px;
        }

        button {
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            transition: transform 0.1s, background 0.2s;
        }
        button:hover { transform: translateY(-2px); }
        button:active { transform: translateY(0); }

        .btn-activate { background-color: var(--beta-color); color: #fff; }
        .btn-bind { background-color: var(--ligand-color); color: #fff; }
        .btn-reset { background-color: #64748b; color: #fff; }

        button:disabled {
            opacity: 0.5;
            cursor: not-allowed;
            transform: none;
        }

        /* --- INFO PANEL --- */
        #info-panel {
            margin-top: 20px;
            background: #334155;
            padding: 20px;
            border-radius: 8px;
            width: 800px;
            box-sizing: border-box;
            border-left: 5px solid var(--alpha-color);
        }
        #info-title { font-weight: bold; color: var(--alpha-color); margin-bottom: 5px; }
        #info-text { line-height: 1.5; font-size: 0.95rem; }

        .legend {
            display: flex;
            gap: 15px;
            margin-top: 10px;
            font-size: 0.8rem;
        }
        .dot { width: 10px; height: 10px; display: inline-block; border-radius: 50%; margin-right: 5px; }

    </style>
</head>
<body>

    <header>
        <h1>CD11b/CD18 Integrin (Mac-1)</h1>
        <p class="subtitle">Interactive visualization of conformational activation and ligand binding</p>
    </header>

    <div id="stage">
        <div id="ligand">Ligand<br><small>(e.g. iC3b)</small></div>

        <div id="integrin">
            <div class="beta-subunit"></div>
            <div class="alpha-subunit">
                <div class="headpiece">
                    <div class="midas-site"></div>
                </div>
            </div>
        </div>

        <div class="membrane"></div>
        <div class="membrane-label">Neutrophil / Macrophage Membrane</div>
    </div>

    <div id="controls">
        <button id="btn-activate" class="btn-activate" onclick="activateIntegrin()">1. Activate (Inside-Out)</button>
        <button id="btn-bind" class="btn-bind" onclick="bindLigand()" disabled>2. Bind Ligand</button>
        <button id="btn-reset" class="btn-reset" onclick="resetSim()">Reset</button>
    </div>

    <div id="info-panel">
        <div id="info-title">Status: Inactive (Bent Conformation)</div>
        <div id="info-text">
            The CD11b/CD18 integrin is currently in a <strong>bent-closed</strong> state. The headpiece (ligand-binding domain) is tucked against the membrane, preventing accidental adhesion to blood vessel walls. This preserves the leukocyte in a "rolling" state.
        </div>
        <div class="legend">
            <span><span class="dot" style="background:var(--alpha-color)"></span>CD11b ($\alpha_M$)</span>
            <span><span class="dot" style="background:var(--beta-color)"></span>CD18 ($\beta_2$)</span>
            <span><span class="dot" style="background:var(--ligand-color)"></span>Ligand (ICAM-1/iC3b)</span>
        </div>
    </div>

    <script>
        // DOM Elements
        const integrin = document.getElementById('integrin');
        const ligand = document.getElementById('ligand');
        const btnActivate = document.getElementById('btn-activate');
        const btnBind = document.getElementById('btn-bind');
        const infoTitle = document.getElementById('info-title');
        const infoText = document.getElementById('info-text');

        let currentState = 'inactive';

        function activateIntegrin() {
            if (currentState !== 'inactive') return;

            // Visual Updates
            integrin.classList.add('active');
            
            // Logic Updates
            currentState = 'active';
            btnActivate.disabled = true;
            btnBind.disabled = false;

            // Text Updates
            infoTitle.textContent = "Status: Activated (Extended-Open)";
            infoText.innerHTML = `
                <strong>Inside-Out Signaling:</strong> Chemokines or inflammatory signals have triggered the cell. 
                The integrin extends ("switchblade motion"), moving from bent to extended. 
                The hybrid domain swings out, opening the <span style="color:#60a5fa">$\alpha$-I domain</span> and exposing the MIDAS site (gold) for high-affinity binding.
            `;
        }

        function bindLigand() {
            if (currentState !== 'active') return;

            // Visual Updates
            ligand.classList.add('bound');
            
            // Wait for transition to simulate binding effect
            setTimeout(() => {
                integrin.classList.add('pulling'); // Simulate tension/signaling
            }, 1000);

            // Logic Updates
            currentState = 'bound';
            btnBind.disabled = true;

            // Text Updates
            infoTitle.textContent = "Status: Ligand Bound & Signaling";
            infoText.innerHTML = `
                <strong>Outside-In Signaling:</strong> The integrin has firmly bound its ligand (e.g., iC3b on a bacterium or ICAM-1 on endothelium).
                This clustering links the integrin to the <em>actin cytoskeleton</em> inside the cell, triggering phagocytosis, cell spreading, or firm adhesion (stopping the cell from rolling).
            `;
        }

        function resetSim() {
            // Remove classes
            integrin.classList.remove('active', 'pulling');
            ligand.classList.remove('bound');

            // Reset Logic
            currentState = 'inactive';
            btnActivate.disabled = false;
            btnBind.disabled = true;

            // Reset Text
            infoTitle.textContent = "Status: Inactive (Bent Conformation)";
            infoText.innerHTML = `
                The CD11b/CD18 integrin is currently in a <strong>bent-closed</strong> state. The headpiece is tucked away to prevent binding. Click "Activate" to simulate an inflammatory trigger.
            `;
        }
    </script>
</body>
</html>

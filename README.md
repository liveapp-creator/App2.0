<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ISLAM AND CO - Booker Portal</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
    <style>
        :root {
            --brand-blue: #1e40af;
            --brand-accent: #2563eb;
            --surface-clean: #ffffff;
            --bg-workspace: #f8fafc;
            --border-elegant: #cbd5e1;
            --text-main: #334155;
            --excel-font: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
            --panel-header-bg: #e0f2fe; 
            --panel-header-border: #bae6fd;
            --input-soft-bg: #f8fafc;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; font-family: var(--excel-font); }
        body { background: var(--bg-workspace); color: var(--text-main); user-select: none; }

        .announcement-banner-strip { background: #0f172a; color: #fef08a; padding: 4px 14px; font-weight: 700; font-size: 11px; display: flex; align-items: center; border-bottom: 1px solid #e2e8f0; height: 28px; }
        .app-fluid-canvas { width: 100%; max-width: 1100px; margin: 0 auto; padding: 10px; padding-bottom: 60px; }
        .screen-view-panel { display: none; }
        .screen-view-panel.view-active { display: block; }

        .secure-auth-card { max-width: 420px; margin: 80px auto 20px auto; background: var(--surface-clean); border-radius: 8px; box-shadow: 0 10px 30px rgba(0,0,0,0.08); border: 1px solid var(--border-elegant); overflow: hidden; }
        .auth-brand-header { background: var(--brand-blue); padding: 25px; text-align: center; color: white; }
        .auth-brand-header h1 { font-size: 28px; font-weight: 900; letter-spacing: 0.5px; }
        .auth-brand-header p { font-size: 11px; color: #93c5fd; margin-top: 4px; text-transform: uppercase; font-weight: 700; }
        .auth-card-body { padding: 25px; }

        .session-runtime-dashboard-strip { background: linear-gradient(90deg, #1e3a8a 0%, #0f172a 100%); color: white; padding: 6px 12px; display: flex; justify-content: space-between; align-items: center; font-size: 11.5px; font-weight: 700; border-radius: 4px; margin-bottom: 4px !important; }
        .logout-action-btn { background: #ef4444; color: white; border: none; padding: 3px 10px; border-radius: 4px; font-size: 11px; cursor: pointer; font-weight: 700; }

        .app-main-title-theme-banner { background: var(--brand-blue); color: white; text-align: center; padding: 10px; border-radius: 4px; margin-bottom: 10px !important; }
        .app-main-title-theme-banner h2 { font-size: 28px; font-weight: 900; letter-spacing: 0.5px; }
        .live-now-badge { display: inline-block; background: #10b981; color: white; padding: 1px 8px; border-radius: 20px; font-size: 10px; font-weight: 800; margin-top: 3px; }
                .workspace-card-section { background: var(--surface-clean); padding: 12px; border-radius: 6px; border: 1px solid var(--border-elegant); margin-bottom: 12px; position: relative; }
        .workspace-card-header-wrapper { display: flex; justify-content: space-between; align-items: center; margin-bottom: 14px; background: var(--panel-header-bg); border: 1px solid var(--panel-header-border); border-left: 5px solid #0284c7; padding: 10px 14px; border-radius: 4px; }
        .workspace-card-section h3 { font-size: 15px; font-weight: 900; color: #0369a1; text-transform: uppercase; letter-spacing: 0.7px; }
        .panel-corner-trash-basket { cursor: pointer; font-size: 11px; padding: 2px 6px; font-weight: 700; border-radius: 3px; background: #fee2e2; border: 1px solid #fca5a5; transition: all 0.2s; display: inline-flex; align-items: center; gap: 3px; color: #b91c1c; }
        .panel-corner-trash-basket:hover { background: #fca5a5; }

        .grid-inline-row-panel { display: flex; flex-direction: row; flex-wrap: nowrap; gap: 8px; align-items: flex-end; width: 100%; margin-bottom: 12px; }
        .node-block-wrapper { display: flex; flex-direction: column; }
        .field-label-node { display: block; font-size: 11px; font-weight: 700; color: #475569; margin-bottom: 4px; text-transform: uppercase; white-space: nowrap; }
        
        .input-control-node { width: 100%; padding: 6px 10px; border: 1px solid var(--border-elegant); border-radius: 4px; font-size: 13px; font-weight: 600; color: #0f172a; background: var(--input-soft-bg); height: 35px; outline: none; }
        .input-control-node:focus { border-color: var(--brand-accent); background: #ffffff; }
        .input-control-node[readonly] { background: #e2e8f0; color: #1e293b; font-weight: 700; }

        .password-input-wrapper { position: relative; width: 100%; }
        .password-toggle-eye { position: absolute; right: 10px; top: 50%; transform: translateY(-50%); cursor: pointer; user-select: none; font-size: 16px; color: #64748b; z-index: 5; }

        .btn-compact-search-action { background: var(--brand-blue); color: white; border: none; padding: 0 20px; height: 35px; font-size: 11.5px; font-weight: 700; border-radius: 4px; cursor: pointer; flex-shrink: 0; }
        .customer-data-grid-layout { display: grid; grid-template-columns: repeat(2, 1fr); gap: 10px; margin-top: 10px; }

        .cart-scroll-container-block { max-height: 380px; overflow-y: auto; border: 1px solid var(--border-elegant); border-radius: 4px; }
        .app-data-grid-table { width: 100%; border-collapse: collapse; }
        .app-data-grid-table th { background: #f1f5f9; color: #475569; font-size: 10.5px; font-weight: 800; text-transform: uppercase; padding: 5px 8px; text-align: left; border-bottom: 2px solid var(--border-elegant); position: sticky; top: 0; z-index: 10; }
        .app-data-grid-table td { padding: 4px 8px; font-size: 11.5px; color: var(--text-main); border-bottom: 1px solid var(--border-elegant); background: #ffffff; font-weight: 600; }
        
        .product-name-single-line-clamp { display: block; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; max-width: 320px; font-size: 12px; font-weight: 700; color: #0f172a; }

        .floating-modal-system-overlay { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(15,23,42,0.6); z-index: 9999; justify-content: center; align-items: center; padding: 15px; }
        .floating-modal-viewport-card { background: var(--surface-clean); width: 100%; max-width: 500px; border-radius: 6px; overflow: hidden; border: 1px solid var(--border-elegant); }
                .floating-modal-header { background: var(--brand-blue); color: white; padding: 10px 15px; font-size: 13px; font-weight: 800; text-align: center; text-transform: uppercase; }
        .floating-modal-body { padding: 15px; }

        .quantity-stepper-wrapper { display: flex; justify-content: center; align-items: center; gap: 12px; margin: 15px 0; }
        .quantity-stepper-btn { width: 38px; height: 38px; background: #e2e8f0; border: none; font-size: 20px; font-weight: 800; border-radius: 4px; cursor: pointer; color: var(--brand-blue); }
        .quantity-stepper-input { width: 70px; text-align: center; font-size: 18px; font-weight: 800; height: 38px; border: 1px solid var(--border-elegant); border-radius: 4px; }
        .btn-ui-action { background: var(--brand-blue); color: white; border: none; padding: 0 14px; height: 35px; font-size: 12px; font-weight: 700; border-radius: 4px; cursor: pointer; display: inline-flex; align-items: center; justify-content: center; text-decoration: none; }

        .excel-invoice-blueprint-viewport { background: #ffffff !important; color: #000000 !important; width: 100%; max-width: 600px; padding: 15px; margin: 0 auto; border: 1px solid #000000 !important; line-height: 1.2; box-sizing: border-box; overflow: hidden; }
        .excel-invoice-blueprint-viewport * { font-family: var(--excel-font) !important; color: #000000 !important; box-sizing: border-box; }
        .blueprint-txt-9x { font-size: 9px !important; color: #000000 !important; }
        .blueprint-txt-12x { font-size: 12px !important; color: #000000 !important; }
        
        .bill-data-table { width: 100%; border-collapse: collapse; margin-top: 5px; font-size: 9px !important; table-layout: fixed; border: none !important; }
        .bill-data-table th { font-weight: bold !important; text-align: left; padding: 3px 2px; border: none !important; border-bottom: 0.5px solid #000000 !important; color: #000000 !important; }
        .bill-data-table td { padding: 3px 2px; border: none !important; border-bottom: 0.5px solid #000000 !important; white-space: normal; word-wrap: break-word; overflow-wrap: break-word; vertical-align: middle !important; color: #000000 !important; }
        
        .bill-totals-alignment-block { display: flex; flex-direction: column; align-items: flex-end; width: 100%; margin-top: 3px; font-size: 9px !important; gap: 1px; }
        .bill-totals-alignment-block > div { display: flex; justify-content: flex-end; align-items: center; width: 100%; color: #000000 !important; }
        .bill-grand-value-container { border: 0.5px solid #000000; padding: 2px 4px; font-weight: bold; margin-top: 1px; font-size: 9px !important; display: inline-block; min-width: 55px; text-align: right; margin-left: 2px; color: #000000 !important; }
        .bill-normal-value-container { padding: 0px 4px; font-weight: normal; font-size: 9px !important; display: inline-block; min-width: 55px; text-align: right; margin-left: 2px; color: #000000 !important; }
        
        .bill-horizontal-logistics-strip { display: flex; flex-direction: row; flex-wrap: nowrap; justify-content: space-between; align-items: flex-start; width: 100%; font-size: 8px !important; gap: 5px; border: none !important; margin-top: 8px; padding-top: 0px; color: #000000 !important; }
        .bill-horizontal-logistics-strip > div { display: flex; flex-direction: column; min-width: 0; word-wrap: break-word; overflow-wrap: break-word; color: #000000 !important; }
        .bill-horizontal-logistics-strip strong { font-weight: bold !important; white-space: nowrap; color: #000000 !important; }
        .bill-horizontal-logistics-strip span { font-weight: normal !important; white-space: nowrap; line-height: 1.1; margin-top: 1px; color: #000000 !important; }

        .info-data-stack { display: flex; flex-direction: column; margin-bottom: 3px; width: 100%; color: #000000 !important; }
        .info-data-stack strong { font-weight: bold !important; font-size: 9px !important; text-transform: uppercase; color: #000000 !important; margin-bottom: 1px; }
        .info-data-stack span { font-weight: normal !important; font-size: 9.5px !important; word-wrap: break-word; overflow-wrap: break-word; white-space: normal; display: block; line-height: 1.2; color: #000000 !important; }

        .history-tabs-container { display: flex; gap: 5px; margin-bottom: 10px; }
        .history-tab-btn { flex: 1; padding: 8px; background: #e2e8f0; border: 1px solid #cbd5e1; border-radius: 4px; font-weight: 700; font-size: 11px; cursor: pointer; text-align: center; }
        .history-tab-btn.active-tab { background: var(--brand-blue); color: white; border-color: var(--brand-blue); }
        .history-content-panel { display: none; margin-top: 10px; }
        .history-content-panel.active-panel { display: block; }
    </style>
</head>
<body>

<div class="announcement-banner-strip" id="globalMarqueeStripContainer" style="display:none;">
    <span style="white-space:nowrap; margin-right:8px; font-weight:900; background:#ef4444; color:white; padding:1px 5px; border-radius:2px; font-size:9px;">ANNOUNCEMENT</span>
    <marquee id="globalPromoMarqueeString" scrollamount="4">System live channels monitoring routing loops...</marquee>
</div>

<div class="app-fluid-canvas">
    <div id="viewPanelLogin" class="screen-view-panel view-active">
        <div class="secure-auth-card">
            <div class="auth-brand-header">
                <h1>ISLAM AND CO</h1>
                <p>Enterprise Dashboard Security Access</p>
            </div>
            <div class="auth-card-body">
                <div style="margin-bottom:12px;">
                    <label class="field-label-node">User Name</label>
                    <input type="text" id="nodeAuthUsername" class="input-control-node" placeholder="Enter security account ID...">
                </div>
                <div style="margin-bottom:16px;">
                    <label class="field-label-node">Password</label>
                    <div class="password-input-wrapper">
                        <input type="password" id="nodeAuthPassword" class="input-control-node" placeholder="Enter access credentials sequence...">
                        <span class="password-toggle-eye" id="togglePasswordVisibilityIcon" onclick="togglePasswordViewField()">👁️</span>
                    </div>
                </div>
                <button class="btn-ui-action" id="btnAuthActionTrigger" style="width:100%; height:38px; font-size:12px;" onclick="validateIdentityAccessGateway()">Login Securely & Sync Data</button>
                <div id="loginFeedbackStatusDisplayBox" style="margin-top:12px; padding:10px; border-radius:4px; display:none; text-align:center; border: 1px solid #ef4444; background: #fee2e2;">
                    <div id="lblSecurityMainErrorString" style="font-size:14px; font-weight:900; color:#b91c1c;"></div>
                    <div id="lblSecuritySubAttemptsString" style="font-size:12px; font-weight:700; color:#334155; margin-top:4px;"></div>
                </div>
            </div>
        </div>
        <div style="text-align: center; font-size: 11px; font-weight: 700; color: #64748b;">® Powered by Shujaat</div>
    </div>
        <div id="viewPanelWorkspace" class="screen-view-panel">
        <div class="session-runtime-dashboard-strip">
            <div>Welcome Booker: <span id="lblActiveRuntimeBookerName">-</span></div>
            <div id="lblLiveClockDisplay">🕒 Connecting session modules...</div>
            <button class="logout-action-btn" onclick="terminateUserSessionState()">Logout Securely 🔒</button>
        </div>

        <div class="app-main-title-theme-banner">
            <h2>ISLAM AND CO</h2>
            <div class="live-now-badge">🟢 Live Now</div>
        </div>

        <div class="workspace-card-section">
            <div class="workspace-card-header-wrapper">
                <h3>Customer Panel</h3>
                <span class="panel-corner-trash-basket" id="btnCornerTrashBasket" title="Clear Fields" onclick="wipeCustomerLayoutFields()">🗑️ Clear</span>
            </div>
            <div class="grid-inline-row-panel">
                <div class="node-block-wrapper" style="width: 130px; flex-shrink: 0;">
                    <label class="field-label-node">Route Mode</label>
                    <select id="selectRouteModeOption" class="input-control-node" style="padding: 6px; font-size:12px;" onchange="adjustCustomerSearchState()">
                        <option value="System">System ID</option>
                        <option value="Manual">Manual ID</option>
                    </select>
                </div>
                <div class="node-block-wrapper" style="flex-grow: 1;">
                    <label class="field-label-node">Outlet Search Box</label>
                    <input type="text" id="inputClientRegistrySearchKey" class="input-control-node" style="font-size:14px; font-weight:700;" placeholder="Search Code..." oninput="handleInstantOnInputSearch()">
                </div>
                <button class="btn-compact-search-action" id="btnExplicitSearchNode" onclick="performCustomerRegistryQuery()">Search</button>
            </div>

            <div class="customer-data-grid-layout">
                <div>
                    <label class="field-label-node">Outlet Name</label>
                    <input type="text" id="fieldUiOutletName" class="input-control-node" oninput="saveCurrentBillStateToLocalMemory()" readonly>
                </div>
                <div>
                    <label class="field-label-node">Outlet Address</label>
                    <input type="text" id="fieldUiOutletAddress" class="input-control-node" oninput="saveCurrentBillStateToLocalMemory()" readonly>
                </div>
                <div>
                    <label class="field-label-node">Contact Number</label>
                    <input type="text" id="fieldUiContactNumber" class="input-control-node" oninput="saveCurrentBillStateToLocalMemory()" readonly>
                </div>
                <div>
                    <label class="field-label-node">Owner Name</label>
                    <input type="text" id="fieldUiOwnerName" class="input-control-node" oninput="saveCurrentBillStateToLocalMemory()" readonly>
                </div>
                <div style="grid-column: span 2;">
                    <label class="field-label-node">Booker Name</label>
                    <input type="text" id="fieldUiActiveBooker" class="input-control-node" readonly>
                </div>
            </div>
        </div>

        <div class="workspace-card-section">
            <div class="workspace-card-header-wrapper">
                <h3>Tax Status Configuration</h3>
            </div>
            <div style="margin-bottom: 10px;">
                <label class="field-label-node">Tax Status (Drop Down List)</label>
                <select id="selectGlobalTaxAppPolicy" class="input-control-node" onchange="executeCalculationsPipeline(); saveCurrentBillStateToLocalMemory();">
                    <option value="Normal">Normal Rate</option>
                    <option value="Filer">Filer Rate</option>
                </select>
            </div>
            <button class="btn-ui-action" style="background:#0284c7; width:100%; height:35px;" onclick="launchRateCatalogModalWindow()">📋 Open Rate List Sheet</button>
        </div>

        <div class="workspace-card-section">
            <div class="workspace-card-header-wrapper">
                <h3>Products Selection Add to Cart</h3>
            </div>
            <div style="margin-bottom: 10px;">
                <label class="field-label-node">Click to Expand Product Drop Down List</label>
                <select id="selectDynamicProductInventoryCatalog" class="input-control-node" onchange="interceptProductSelectionEvent()">
                </select>
            </div>
            <div class="cart-scroll-container-block">
                <table class="app-data-grid-table">
                    <thead>
                        <tr>
                            <th>Products Name</th>
                            <th style="width: 80px;">Quantity</th>
                            <th style="width: 90px;">Discount</th>
                            <th style="width: 110px;">Net Amount</th>
                            <th style="width: 70px; text-align: center;">Action</th>
                        </tr>
                    </thead>
                    <tbody id="domTableBodySalesBasket"></tbody>
                </table>
            </div>
        </div>
                <div style="display: flex; gap: 10px; margin-bottom: 10px;">
            <button class="btn-ui-action" style="background: #ef4444; flex: 1; height: 38px;" onclick="clearEntireActiveBillData()">🗑️ Clear Entire Bill</button>
            <button class="btn-ui-action" style="background: #0f172a; flex: 1; height: 38px;" onclick="openHistorySystemModalWindow()">⏳ Open History Module</button>
        </div>

        <div class="workspace-card-section" style="background:#cbd5e1;">
            <div class="workspace-card-header-wrapper" style="background: #cbd5e1; border-color: #94a3b8; border-left-color: #0f172a;">
                <h3 style="color:#0f172a;">Live Bill System Viewport</h3>
            </div>
            
            <div id="invoicePrintCaptureTargetCanvas" class="excel-invoice-blueprint-viewport">
                <div style="display:flex; justify-content:space-between; align-items: center; width:100%;">
                    <div class="blueprint-txt-12x" style="font-weight: bold; letter-spacing:0.3px; color: #000000 !important;">ISLAM AND CO.</div>
                    <div class="blueprint-txt-12x" style="font-weight: bold; color: #000000 !important;">SALE INVOICE</div>
                </div>
                
                <div class="blueprint-txt-9x" style="text-align: center; width:100%; font-weight: normal; margin: 1px 0; color: #000000 !important;" id="billTimestampNode">-</div>
                
                <div class="blueprint-txt-9x" style="line-height: 1.2; margin-bottom: 4px; color: #000000 !important;">
                    <strong style="color: #000000 !important;">Distributor CNIC :</strong> 37202-4977404-3<br>
                    <strong style="color: #000000 !important;">Distributor NTN :</strong> A-48299<br>
                    <strong style="color: #000000 !important;">Distributor STRN :</strong> 9000<br>
                    <strong style="color: #000000 !important;">Distributor Address :</strong> CHOA SAIDAN SHAH, CHAKWAL
                </div>
                
                <div style="display:flex; gap:30px; margin: 2px 0; color: #000000 !important;" class="blueprint-txt-9x">
                    <div><strong style="color: #000000 !important;">Dispatch#</strong> <span id="billDispatchRandomKey" style="color: #000000 !important;">-</span></div>
                    <div><strong style="color: #000000 !important;">Invoice#</strong> <span id="billInvoiceRandomKey" style="color: #000000 !important;">-</span></div>
                </div>
                
                <div style="width:100%; height:0.5px; background:#000000; margin: 4px 0;"></div>
                
                <div style="display:grid; grid-template-columns: 1.1fr 0.9fr; width:100%; margin-bottom:4px; gap:10px;" class="blueprint-txt-9x">
                    <div style="display: flex; flex-direction: column; min-width: 0;">
                        <div class="info-data-stack"><strong style="color:#000000 !important;">Outlet ID</strong><span id="billOutId" style="color:#000000 !important;">-</span></div>
                        <div class="info-data-stack"><strong style="color:#000000 !important;">Outlet Name</strong><span id="billOutName" style="color:#000000 !important;">-</span></div>
                        <div class="info-data-stack"><strong style="color:#000000 !important;">Address</strong><span id="billOutAddress" style="color:#000000 !important;">-</span></div>
                        <div class="info-data-stack"><strong style="color:#000000 !important;">Tax Status</strong><span id="billOutTaxStatus" style="color:#000000 !important;">-</span></div>
                    </div>
                    <div style="display: flex; flex-direction: column; min-width: 0; align-items: flex-end; text-align: right;">
                        <div class="info-data-stack"><strong style="color:#000000 !important;">Owner Name</strong><span id="billOutOwner" style="color:#000000 !important;">-</span></div>
                        <div class="info-data-stack"><strong style="color:#000000 !important;">Contact No</strong><span id="billOutPhone" style="color:#000000 !important;">-</span></div>
                    </div>
                </div>

                <table class="bill-data-table">
                    <thead>
                        <tr>
                            <th style="width:36%; color:#000000 !important;">Pack name</th>
                            <th style="width:10%; text-align: center; color:#000000 !important;">Qty</th>
                            <th style="width:13%; text-align: right; color:#000000 !important;">Rate</th>
                            <th style="width:14%; text-align: right; color:#000000 !important;">Amount</th>
                            <th style="width:14%; text-align: right; color:#000000 !important;">Discount</th>
                            <th style="width:13%; text-align: right; color:#000000 !important;">NTP</th>
                        </tr>
                    </thead>
                    <tbody id="billTableItemsDataBody"></tbody>
                </table>

                <div class="bill-totals-alignment-block">
                    <div><strong style="color:#000000 !important;">Gross Amount:</strong><span class="bill-normal-value-container" style="color:#000000 !important;" id="billSummaryGrossAmount">0</span></div>
                    <div><strong style="color:#000000 !important;">Promo:</strong><span class="bill-normal-value-container" style="color:#000000 !important;" id="billSummaryPromoAmount">0</span></div>
                    <div><strong style="color:#000000 !important;">Discount:</strong><span class="bill-normal-value-container" style="color:#000000 !important;" id="billSummaryTotalDiscount">0</span></div>
                    <div><strong style="color:#000000 !important;">Advance income tax ():</strong><span class="bill-normal-value-container" style="color:#000000 !important;" id="billSummaryAdvanceTax">0</span></div>
                    <div><strong style="color:#000000 !important;">Net Amount:</strong><span class="bill-grand-value-container" style="border-color:#000000; color:#000000 !important; font-weight: bold !important;" id="billSummaryGrandNet">0</span></div>
                </div>

                <div class="bill-horizontal-logistics-strip">
                    <div><strong style="color:#000000 !important;">User:</strong><span id="billLogisticsUser" style="color:#000000 !important;">Shujaat Raja</span></div>
                    <div><strong style="color:#000000 !important;">Booker:</strong><span id="billLogisticsBooker" style="color:#000000 !important;">-</span></div>
                    <div><strong style="color:#000000 !important;">Driver:</strong><span id="billLogisticsDriver" style="color:#000000 !important;">-</span></div>
                    <div><strong style="color:#000000 !important;">Veh#:</strong><span id="billLogisticsVeh" style="color:#000000 !important;">-</span></div>
                    <div><strong style="color:#000000 !important;">PJP:</strong><span id="billLogisticsPjp" style="color:#000000 !important;">-</span></div>
                    <div style="flex-grow: 1; text-align: right;"><strong style="color:#000000 !important;">Expected Delivery Date:</strong><span id="billLogisticsDeliveryDate" style="color:#000000 !important;">-</span></div>
                </div>
            </div>
            <br>
            <button class="btn-ui-action" style="background:#0284c7; width:100%; height:35px;" onclick="downloadBillSnapshotJpgFile()">Download Bill Snapshot Image 📸</button>
        </div>

        <div class="workspace-card-section">
            <div class="workspace-card-header-wrapper">
                <h3>Bill WhatsApp System</h3>
            </div>
            <div style="margin-bottom:10px;">
                <label class="field-label-node">Select Target Staff Recipient</label>
                <select id="selectWhatsAppStaffMemberNode" class="input-control-node">
                    <option value="923465846781">👤 Asiam Hussain</option>
                    <option value="923415011140">👤 Adnan Hassan</option>
                    <option value="923061645603">👤 Saqib Abbas</option>
                    <option value="923461649698">👤 Arslan Sajid</option>
                    <option value="923150564149">👤 Asim Raza</option>
                    <option value="923105714429">👤 Naqeeb Ur Rehman</option>
                </select>
            </div>
            <button class="btn-ui-action" style="background:#16a34a; width:100%; height:38px; font-size:13px;" onclick="commitRecordAndTransmitWhatsAppMessage()">Transmit Order Blueprint via WhatsApp 🚀</button>
        </div>
    </div>
</div>
<div id="modalOverlayQuantityStepper" class="floating-modal-system-overlay">
    <div class="floating-modal-viewport-card">
        <div class="floating-modal-header" id="stepHeaderProductName">Adjust Quantity Matrix</div>
        <div class="floating-modal-body">
            <div id="stepLabelProductRates" style="text-align:center; font-size:12px; font-weight:700; color:#475569; margin-bottom:8px;">-</div>
            <div class="quantity-stepper-wrapper">
                <button class="quantity-stepper-btn" onclick="modifyStepperCounterNode(-1)">-</button>
                <input type="number" id="inputStepperManualValue" class="quantity-stepper-input" value="1" min="1">
                <button class="quantity-stepper-btn" onclick="modifyStepperCounterNode(1)">+</button>
            </div>
            <button class="btn-ui-action" style="background:#16a34a; width:100%; height:35px;" onclick="commitStepperItemToSalesBasketArray()">Add to Cart 🛒</button>
            <button class="btn-ui-action" style="background:#e2e8f0; color:#334155; width:100%; height:35px; margin-top:6px;" onclick="closeQuantityStepperModalWindow()">Cancel & Exit</button>
        </div>
    </div>
</div>

<div id="modalOverlayRateCatalog" class="floating-modal-system-overlay">
    <div class="floating-modal-viewport-card" style="max-width:500px;">
        <div class="floating-modal-header">System Active Rate List Sheet</div>
        <div class="floating-modal-body" style="padding: 8px;">
            <div style="max-height: 280px; overflow-y: auto; border: 1px solid var(--border-elegant);">
                <div style="display: grid; grid-template-columns: 2fr 1fr 1fr 1fr; background: #e2e8f0; padding: 6px; font-size: 11px; font-weight: 800;">
                    <div>Product</div><div>Normal</div><div>Disc</div><div>Filer</div>
                </div>
                <div id="containerRateCatalogModalInjectTarget"></div>
            </div>
            <button class="btn-ui-action" style="background:#ef4444; width:100%; height:35px; margin-top:8px;" onclick="closeRateCatalogModalWindow()">Close Sheet</button>
        </div>
    </div>
</div>

<div id="modalOverlayHistorySystem" class="floating-modal-system-overlay">
    <div class="floating-modal-viewport-card" style="max-width:650px; width: 95%;">
        <div class="floating-modal-header">⏳ History & Date-Range Collection Module</div>
        <div class="floating-modal-body" style="padding: 12px;">
            <div style="margin-bottom: 12px; display: flex; flex-direction: column; gap: 8px; background: #f1f5f9; padding: 10px; border-radius: 4px;">
                <div style="display: flex; gap: 8px; align-items: center; flex-wrap: wrap;">
                    <label class="field-label-node" style="margin-bottom:0;">From:</label>
                    <input type="date" id="historyFilterFromDate" class="input-control-node" style="height:32px; width:135px; padding:2px 5px;" onchange="renderHistoryModuleViews()">
                    <label class="field-label-node" style="margin-bottom:0;">To:</label>
                    <input type="date" id="historyFilterToDate" class="input-control-node" style="height:32px; width:135px; padding:2px 5px;" onchange="renderHistoryModuleViews()">
                    <button class="btn-ui-action" style="background:#ef4444; height:32px; font-size:11px; margin-left:auto;" onclick="purgeAllHistoryLogsWithConfirmation()">⚠️ Delete All</button>
                </div>
                <div style="font-size: 12px; font-weight: 800; color: #1e40af; border-top: 1px solid #cbd5e1; padding-top: 5px;" id="lblRangeHistoryTotalAmount">
                    Total Amount In Selected Period: Rs. 0
                </div>
            </div>
            <div class="history-tabs-container">
                <div id="tabHistoryPickList" class="history-tab-btn active-tab" onclick="switchHistoryActiveTab('PickList')">📦 Pick List (Loadout)</div>
                <div id="tabHistoryPreview" class="history-tab-btn" onclick="switchHistoryActiveTab('Preview')">📄 Bill Preview List</div>
            </div>
            <div id="panelHistoryPickList" class="history-content-panel active-panel">
                <div style="background:#fff; border:1px solid #cbd5e1; padding:10px; border-radius:4px; max-height:240px; overflow-y:auto; font-size:12px;" id="historyPickListContainer"></div>
                <button class="btn-ui-action" style="background:#16a34a; width:100%; height:35px; margin-top:8px;" onclick="exportPickListToExcelFormat()">📥 Export Pick List To Excel</button>
            </div>
            <div id="panelHistoryPreview" class="history-content-panel">
                <div style="background:#fff; border:1px solid #cbd5e1; padding:5px; border-radius:4px; max-height:240px; overflow-y:auto;">
                    <table class="app-data-grid-table" style="font-size:11.5px;">
                        <thead>
                            <tr>
                                <th>Inv ID</th>
                                <th>Outlet Name</th>
                                <th>Net Bill</th>
                                <th style="text-align:center;">Action</th>
                            </tr>
                        </thead>
                        <tbody id="historyBillPreviewTableBodyTarget"></tbody>
                    </table>
                </div>
            </div>
            <button class="btn-ui-action" style="background:#475569; width:100%; height:35px; margin-top:12px;" onclick="closeHistorySystemModalWindow()">Close Module Panel</button>
        </div>
    </div>
</div>

<script>
    const DEPLOYED_GAS_API_ENDPOINT = "https://script.google.com/macros/s/AKfycbzxtpaK8kVOnHJ_ccEtbOSQLmJqJeT1kUp2HAYaBxchNEqfiNK-v7DjSiNtrR4IXbEdMw/exec";

    let cachedSystemMasterDataPayload = null;
    let localActiveSalesBasketArray = [];
    let authenticatedUserBookerString = "";
    
    let stateInvoiceRandomKey = "";
    let stateDispatchRandomKey = "";
    let stateDriverRandomString = "";
    let stateVehRandomString = "";
    let statePjpRandomString = "";
    let stateUserRandomString = "Shujaat Raja";
    
    let activeInterceptionItemContext = null;
    let autoTypingDebounceTimer;
    let currentActiveHistoryTab = "PickList";

    window.addEventListener('DOMContentLoaded', function() {
        initiateLiveSystemTimeStream();
        const today = new Date().toISOString().split('T')[0];
        document.getElementById("historyFilterFromDate").value = today;
        document.getElementById("historyFilterToDate").value = today;

        const persistentToken = localStorage.getItem("islam_co_token_secure_2026");
        if (persistentToken) {
            authenticatedUserBookerString = persistentToken;
            routeInterfaceToWorkspaceView();
            loadSavedBillStateFromLocalMemory();
        }
        
        const storedLocalMemoryCache = localStorage.getItem("islam_co_master_cache_2026");
        if (storedLocalMemoryCache) {
            cachedSystemMasterDataPayload = JSON.parse(storedLocalMemoryCache);
            renderSystemPromoMarqueeComponent();
            buildProductDropdownMenuOptions();
        }
    });
        function validateIdentityAccessGateway() {
        const warningContainer = document.getElementById("loginFeedbackStatusDisplayBox");
        const mainErrorLabel = document.getElementById("lblSecurityMainErrorString");
        const actionBtn = document.getElementById("btnAuthActionTrigger");

        const userValue = document.getElementById("nodeAuthUsername").value.trim();
        const passValue = document.getElementById("nodeAuthPassword").value.trim();

        if (!userValue || !passValue) { return alert("Please enter username and password."); }

        let storedAttempts = parseInt(sessionStorage.getItem("islam_co_wrong_attempts_" + userValue)) || 0;
        if (storedAttempts >= 3) {
            warningContainer.style.display = "block"; mainErrorLabel.innerText = "Terminal Blocked!";
            return alert("❌ Apka Terminal Block ho chuka hai!");
        }

        actionBtn.innerText = "Processing Access Authorization..."; actionBtn.disabled = true;

        executeCrossDomainJsonpTransaction({ action: "loginAuthValidation", user: userValue, pass: passValue, deviceId: "Enterprise-Core" }, function(response) {
            let statusResult = response ? response.status : "failed";
            
            if (statusResult === "blocked" || response?.userStatus === "Blocked") {
                actionBtn.innerText = "Login Securely & Sync Data"; actionBtn.disabled = false;
                warningContainer.style.display = "block"; mainErrorLabel.innerText = "Apki ID Block Hai!";
                return alert("❌ Apki ID Block Hai!");
            }

            if (statusResult === "success") {
                sessionStorage.removeItem("islam_co_wrong_attempts_" + userValue);
                authenticatedUserBookerString = response.bookerName || userValue;
                localStorage.setItem("islam_co_token_secure_2026", authenticatedUserBookerString);
                
                executeCrossDomainJsonpTransaction({ action: "fetchAllSyncDataPack" }, function(incomingPayload) {
                    actionBtn.innerText = "Login Securely & Sync Data"; actionBtn.disabled = false;
                    if (incomingPayload && incomingPayload.status === "success") {
                        cachedSystemMasterDataPayload = incomingPayload;
                        localStorage.setItem("islam_co_master_cache_2026", JSON.stringify(incomingPayload));
                        renderSystemPromoMarqueeComponent();
                        buildProductDropdownMenuOptions();
                        routeInterfaceToWorkspaceView();
                    } else {
                        routeInterfaceToWorkspaceView();
                    }
                });
            } else {
                actionBtn.innerText = "Login Securely & Sync Data"; actionBtn.disabled = false;
                storedAttempts++;
                sessionStorage.setItem("islam_co_wrong_attempts_" + userValue, storedAttempts);
                let remaining = 3 - storedAttempts;
                warningContainer.style.display = "block";
                mainErrorLabel.innerText = `Wrong Credentials! (${remaining} attempts left)`;
                alert(`⚠️ Password wrong! Sirf ${remaining} attempts baqi hain.`);
            }
        });
    }

    function togglePasswordViewField() {
        const field = document.getElementById("nodeAuthPassword");
        const icon = document.getElementById("togglePasswordVisibilityIcon");
        if (field.type === "password") { field.type = "text"; icon.innerText = "🕶️"; } 
        else { field.type = "password"; icon.innerText = "👁️"; }
    }

    function initiateLiveSystemTimeStream() {
        setInterval(() => {
            const now = new Date();
            document.getElementById("lblLiveClockDisplay").innerText = "🕒 " + now.toLocaleString('en-US', { hour12: true });
            let formattedDate = now.toLocaleString('en-GB', { day:'2-digit', month:'2-digit', year:'numeric' }) + " " + now.toLocaleTimeString('en-US', { hour: '2-digit', minute: '2-digit', hour12: true });
            if(document.getElementById("billTimestampNode")) { document.getElementById("billTimestampNode").innerText = formattedDate; }
        }, 1000);
    }

    function executeCrossDomainJsonpTransaction(paramsObj, runtimeCallback) {
        const generatedCallbackUid = 'islam_co_cb_' + Math.random().toString(36).substr(2, 9);
        window[generatedCallbackUid] = function(data) {
            runtimeCallback(data); document.body.removeChild(carrierScript); delete window[generatedCallbackUid];
        };
        const queryStringParams = new URLSearchParams({...paramsObj, callback: generatedCallbackUid}).toString();
        const carrierScript = document.createElement('script');
        carrierScript.src = `${DEPLOYED_GAS_API_ENDPOINT}?${queryStringParams}`;
        document.body.appendChild(carrierScript);
    }

    function routeInterfaceToWorkspaceView() {
        document.getElementById("viewPanelLogin").classList.remove("view-active");
        document.getElementById("viewPanelWorkspace").classList.add("view-active");
        document.getElementById("lblActiveRuntimeBookerName").innerText = authenticatedUserBookerString;
        document.getElementById("fieldUiActiveBooker").value = authenticatedUserBookerString;

        if(!stateInvoiceRandomKey) {
            stateDispatchRandomKey = Math.floor(10000000000000 + Math.random() * 90000000000000).toString();
            stateInvoiceRandomKey = Math.floor(100000 + Math.random() * 899999).toString();
            const driversList = ["Muhammad Shabbir", "Bilal Hassan", "Raja Zeeshan", "Raja Irfan", "Nouman Hayyat"];
            stateDriverRandomString = driversList[Math.floor(Math.random() * driversList.length)];
            const requestedVehiclesPool = ["1715", "7650", "183", "9044", "9787"];
            stateVehRandomString = requestedVehiclesPool[Math.floor(Math.random() * requestedVehiclesPool.length)];
            statePjpRandomString = Math.floor(1000 + Math.random() * 9000).toString();
        }
        document.getElementById("billInvoiceRandomKey").innerText = stateInvoiceRandomKey;
        document.getElementById("billDispatchRandomKey").innerText = stateDispatchRandomKey;
        setTimeout(function() { executeCalculationsPipeline(); }, 100);
    }

    function renderSystemPromoMarqueeComponent() {
        if (cachedSystemMasterDataPayload && cachedSystemMasterDataPayload.promoMarquee) {
            document.getElementById("globalMarqueeStripContainer").style.display = "flex";
            document.getElementById("globalPromoMarqueeString").innerText = cachedSystemMasterDataPayload.promoMarquee;
        }
    }

    function adjustCustomerSearchState() {
        const mode = document.getElementById("selectRouteModeOption").value;
        const targetIds = ["fieldUiOutletName", "fieldUiOutletAddress", "fieldUiContactNumber", "fieldUiOwnerName"];
        const explicitSearchBtn = document.getElementById("btnExplicitSearchNode");
        targetIds.forEach(id => {
            const el = document.getElementById(id);
            if (mode === "Manual") { el.readOnly = false; el.style.background = "#ffffff"; explicitSearchBtn.style.display = "none"; } 
            else { el.readOnly = true; el.style.background = "#e2e8f0"; explicitSearchBtn.style.display = "inline-block"; }
        });
        wipeCustomerLayoutFields();
    }

    function handleInstantOnInputSearch() {
        const mode = document.getElementById("selectRouteModeOption").value;
        const searchKey = document.getElementById("inputClientRegistrySearchKey").value.trim();
        document.getElementById("billOutId").innerText = searchKey || "-";
        if (mode === "Manual") {
            clearTimeout(autoTypingDebounceTimer);
            autoTypingDebounceTimer = setTimeout(function() { executeCalculationsPipeline(); saveCurrentBillStateToLocalMemory(); }, 300);
        }
    }

    function performCustomerRegistryQuery() {
        const searchKey = document.getElementById("inputClientRegistrySearchKey").value.trim();
        if (!searchKey) return alert("Search identifier sequence absent.");
        document.getElementById("billOutId").innerText = searchKey;
        let match = cachedSystemMasterDataPayload?.masterData?.find(o => o.outletId.toLowerCase() === searchKey.toLowerCase());
        if (match) {
            document.getElementById("fieldUiOutletName").value = match.outletName;
            document.getElementById("fieldUiOutletAddress").value = match.outletAddress;
            document.getElementById("fieldUiContactNumber").value = match.contactNumber;
            document.getElementById("fieldUiOwnerName").value = match.ownerName;
            document.getElementById("selectGlobalTaxAppPolicy").value = match.filerNonfiler.toLowerCase().includes("non") ? "Normal" : "Filer";
            executeCalculationsPipeline(); saveCurrentBillStateToLocalMemory();
        } else { alert("No data maps found in active storage."); }
    }

    function wipeCustomerLayoutFields() {
        ["fieldUiOutletName", "fieldUiOutletAddress", "fieldUiContactNumber", "fieldUiOwnerName", "inputClientRegistrySearchKey"].forEach(id => document.getElementById(id).value = "");
        document.getElementById("billOutId").innerText = "-"; executeCalculationsPipeline(); saveCurrentBillStateToLocalMemory();
    }

    function launchRateCatalogModalWindow() {
        const pane = document.getElementById("containerRateCatalogModalInjectTarget"); pane.innerHTML = "";
        cachedSystemMasterDataPayload?.rates?.forEach(item => {
            pane.innerHTML += `<div style="display:grid; grid-template-columns: 2fr 1fr 1fr 1fr; padding:5px; font-size:11px; border-bottom:1px solid #e2e8f0;"><div>${item.packName}</div><div>${item.rate}</div><div>${item.discount}</div><div>${item.filer}</div></div>`;
        });
        document.getElementById("modalOverlayRateCatalog").style.display = "flex";
    }
    function closeRateCatalogModalWindow() { document.getElementById("modalOverlayRateCatalog").style.display = "none"; }

    function buildProductDropdownMenuOptions() {
        const menuNode = document.getElementById("selectDynamicProductInventoryCatalog"); if(!menuNode) return;
        menuNode.innerHTML = "<option value=''>-- Click to Expand Product Drop Down List Items Sheet --</option>";
        cachedSystemMasterDataPayload?.rates?.forEach(item => {
            menuNode.innerHTML += `<option value="${escape(item.packName)}|${item.rate}|${item.discount}|${item.filer}">${item.packName}</option>`;
        });
    }

    function interceptProductSelectionEvent() {
        const packedString = document.getElementById("selectDynamicProductInventoryCatalog").value; if (!packedString) return;
        const parts = packedString.split("|");
        activeInterceptionItemContext = { packName: unescape(parts[0]), normalRate: parseFloat(parts[1]), sheetDiscount: parseFloat(parts[2]), filerRate: parseFloat(parts[3]) };
        document.getElementById("stepHeaderProductName").innerText = activeInterceptionItemContext.packName;
        document.getElementById("stepLabelProductRates").innerText = `Normal Rate: Rs.${activeInterceptionItemContext.normalRate} / Filer Rate: Rs.${activeInterceptionItemContext.filerRate}`;
        document.getElementById("inputStepperManualValue").value = "1"; document.getElementById("modalOverlayQuantityStepper").style.display = "flex";
    }

    function closeQuantityStepperModalWindow() {
        document.getElementById("modalOverlayQuantityStepper").style.display = "none"; document.getElementById("selectDynamicProductInventoryCatalog").value = "";
    }

    function modifyStepperCounterNode(offset) {
        let node = document.getElementById("inputStepperManualValue");
        let val = (parseInt(node.value) || 1) + offset; if (val < 1) val = 1; node.value = val;
    }

    function commitStepperItemToSalesBasketArray() {
        const qty = parseInt(document.getElementById("inputStepperManualValue").value) || 1; if (!activeInterceptionItemContext) return;
        let existingItem = localActiveSalesBasketArray.find(item => item.packName === activeInterceptionItemContext.packName);
        if (existingItem) { existingItem.quantity += qty; } 
        else {
            localActiveSalesBasketArray.push({
                packName: activeInterceptionItemContext.packName, normalRate: activeInterceptionItemContext.normalRate,
                sheetDiscount: activeInterceptionItemContext.sheetDiscount, filerRate: activeInterceptionItemContext.filerRate, quantity: qty
            });
        }
        closeQuantityStepperModalWindow(); executeCalculationsPipeline(); saveCurrentBillStateToLocalMemory();
    }

    function executeCalculationsPipeline() {
        const taxRule = document.getElementById("selectGlobalTaxAppPolicy").value;
        let qtyTotal = 0, grossTotal = 0, discTotal = 0, promoTotal = 0, netTotal = 0;
        const cartTarget = document.getElementById("domTableBodySalesBasket"); const billTarget = document.getElementById("billTableItemsDataBody");
        
        if(cartTarget) cartTarget.innerHTML = ""; if(billTarget) billTarget.innerHTML = "";

        const outId = document.getElementById("inputClientRegistrySearchKey")?.value || "-";
        const outName = document.getElementById("fieldUiOutletName")?.value || "-";
        const outAddr = document.getElementById("fieldUiOutletAddress")?.value || "-";
        const outOwner = document.getElementById("fieldUiOwnerName")?.value || "-";
        const outPhone = document.getElementById("fieldUiContactNumber")?.value || "-";

        if(document.getElementById("billOutId")) document.getElementById("billOutId").innerText = outId;
        if(document.getElementById("billOutName")) document.getElementById("billOutName").innerText = outName;
        if(document.getElementById("billOutAddress")) document.getElementById("billOutAddress").innerText = outAddr;
        if(document.getElementById("billOutOwner")) document.getElementById("billOutOwner").innerText = outOwner;
        if(document.getElementById("billOutPhone")) document.getElementById("billOutPhone").innerText = outPhone;
        if(document.getElementById("billOutTaxStatus")) document.getElementById("billOutTaxStatus").innerText = taxRule;
        if(document.getElementById("billLogisticsBooker")) document.getElementById("billLogisticsBooker").innerText = authenticatedUserBookerString || "-";
        if(document.getElementById("billLogisticsDriver")) document.getElementById("billLogisticsDriver").innerText = stateDriverRandomString || "-";
        if(document.getElementById("billLogisticsVeh")) document.getElementById("billLogisticsVeh").innerText = stateVehRandomString || "-";
        if(document.getElementById("billLogisticsPjp")) document.getElementById("billLogisticsPjp").innerText = statePjpRandomString || "-";
        if(document.getElementById("billLogisticsUser")) document.getElementById("billLogisticsUser").innerText = stateUserRandomString;
        
        const d = new Date(); d.setDate(d.getDate() + 1);
        if(document.getElementById("billLogisticsDeliveryDate")) document.getElementById("billLogisticsDeliveryDate").innerText = d.toLocaleDateString('en-GB');

        localActiveSalesBasketArray.forEach((row, rIdx) => {
            let rate = (taxRule === "Filer") ? row.filerRate : row.normalRate;
            let disc = (taxRule === "Filer") ? 0 : row.sheetDiscount;
            let gross = rate * row.quantity; let discLess = disc * row.quantity; let net = gross - discLess;
            qtyTotal += row.quantity; grossTotal += gross; discTotal += discLess; netTotal += net;

            if(cartTarget) {
                cartTarget.innerHTML += `<tr><td><span class="product-name-single-line-clamp" title="${row.packName}">${row.packName}</span></td><td>${row.quantity} Pcs</td><td>Rs. ${discLess}</td><td><strong>Rs. ${net}</strong></td><td style="text-align: center;"><button class="btn-ui-action" style="background:#ef4444; height:22px; font-size:10px; padding:0 6px;" onclick="purgeTargetBasketItemRow(${rIdx})">Remove</button></td></tr>`;
            }
            if(billTarget) {
                billTarget.innerHTML += `<tr><td style="color:#000000 !important;">${row.packName}</td><td style="text-align: center; color:#000000 !important;">${row.quantity}</td><td style="text-align: right; color:#000000 !important;">${rate}</td><td style="text-align: right; color:#000000 !important;">${gross}</td><td style="text-align: right; color:#000000 !important;">${discLess > 0 ? discLess : '-'}</td><td style="text-align: right; font-weight: normal !important; color:#000000 !important;">${net}</td></tr>`;
            }
        });

        if(localActiveSalesBasketArray.length > 0 && billTarget) {
            billTarget.innerHTML += `<tr style="font-weight: bold; background: #ffffff; border-bottom: 0.5px solid #000000 !important;"><td style="color:#000000 !important;">Total</td><td style="text-align: center; color:#000000 !important;">${qtyTotal}</td><td colspan="4"></td></tr>`;
        }
        if(document.getElementById("billSummaryGrossAmount")) document.getElementById("billSummaryGrossAmount").innerText = grossTotal;
        if(document.getElementById("billSummaryPromoAmount")) document.getElementById("billSummaryPromoAmount").innerText = promoTotal;
        if(document.getElementById("billSummaryTotalDiscount")) document.getElementById("billSummaryTotalDiscount").innerText = discTotal;
        if(document.getElementById("billSummaryAdvanceTax")) document.getElementById("billSummaryAdvanceTax").innerText = "0";
        if(document.getElementById("billSummaryGrandNet")) document.getElementById("billSummaryGrandNet").innerText = netTotal;
    }

    document.addEventListener("contextmenu", e => e.preventDefault());
    function purgeTargetBasketItemRow(index) { localActiveSalesBasketArray.splice(index, 1); executeCalculationsPipeline(); saveCurrentBillStateToLocalMemory(); }

    function saveCurrentBillStateToLocalMemory() {
        const statePayload = {
            basket: localActiveSalesBasketArray, routeMode: document.getElementById("selectRouteModeOption").value,
            searchKey: document.getElementById("inputClientRegistrySearchKey").value, outName: document.getElementById("fieldUiOutletName").value,
            outAddr: document.getElementById("fieldUiOutletAddress").value, outPhone: document.getElementById("fieldUiContactNumber").value,
            outOwner: document.getElementById("fieldUiOwnerName").value, taxPolicy: document.getElementById("selectGlobalTaxAppPolicy").value,
            invoiceKey: stateInvoiceRandomKey, dispatchKey: stateDispatchRandomKey, driver: stateDriverRandomString, veh: stateVehRandomString, pjpKey: statePjpRandomString
        };
        localStorage.setItem("islam_co_active_bill_state", JSON.stringify(statePayload));
    }

    function loadSavedBillStateFromLocalMemory() {
        const data = localStorage.getItem("islam_co_active_bill_state");
        if(data) {
            try {
                const parsed = JSON.parse(data); localActiveSalesBasketArray = parsed.basket || [];
                document.getElementById("selectRouteModeOption").value = parsed.routeMode || "System";
                document.getElementById("inputClientRegistrySearchKey").value = parsed.searchKey || "";
                document.getElementById("fieldUiOutletName").value = parsed.outName || "";
                document.getElementById("fieldUiOutletAddress").value = parsed.outAddr || "";
                document.getElementById("fieldUiContactNumber").value = parsed.outPhone || "";
                document.getElementById("fieldUiOwnerName").value = parsed.outOwner || "";
                document.getElementById("selectGlobalTaxAppPolicy").value = parsed.taxPolicy || "Normal";
                stateInvoiceRandomKey = parsed.invoiceKey || ""; stateDispatchRandomKey = parsed.dispatchKey || "";stateDriverRandomString = parsed.driver || ""; stateVehRandomString = parsed.veh || ""; statePjpRandomString = parsed.pjpKey || "";
                executeCalculationsPipeline();
            } catch(e) { console.error(e); }
        }
    }

    function clearEntireActiveBillData() {
        localActiveSalesBasketArray = [];
        stateInvoiceRandomKey = Math.floor(100000 + Math.random() * 899999).toString();
        stateDispatchRandomKey = Math.floor(10000000000000 + Math.random() * 90000000000000).toString();
        document.getElementById("billInvoiceRandomKey").innerText = stateInvoiceRandomKey;
        document.getElementById("billDispatchRandomKey").innerText = stateDispatchRandomKey;
        wipeCustomerLayoutFields(); localStorage.removeItem("islam_co_active_bill_state");
        alert("✅ Bill cache data directly and successfully wiped out!");
    }

    function commitBillRecordToLocalHistoryLogs() {
        const outletIdVal = document.getElementById("inputClientRegistrySearchKey").value.trim() || "-";
        const outletNameVal = document.getElementById("fieldUiOutletName").value.trim() || "Manual Out";
        if(localActiveSalesBasketArray.length === 0) return;
        const todayDateStr = new Date().toISOString().split('T')[0];
        const logItem = {
            invoiceId: stateInvoiceRandomKey, dispatchId: stateDispatchRandomKey, date: todayDateStr,
            time: new Date().toLocaleTimeString('en-US', { hour: '2-digit', minute: '2-digit', hour12: true }),
            outletId: outletIdVal, outletName: outletNameVal, outletAddress: document.getElementById("fieldUiOutletAddress").value,
            ownerName: document.getElementById("fieldUiOwnerName").value, contactNumber: document.getElementById("fieldUiContactNumber").value,
            taxPolicy: document.getElementById("selectGlobalTaxAppPolicy").value, bookerName: authenticatedUserBookerString,
            driverName: stateDriverRandomString, vehicleNo: stateVehRandomString, pjpCode: statePjpRandomString,
            basketItems: JSON.parse(JSON.stringify(localActiveSalesBasketArray)), totalNetBill: document.getElementById("billSummaryGrandNet").innerText
        };
        let activeLogs = []; const existingLogs = localStorage.getItem("islam_co_history_logs_v1");
        if(existingLogs) { activeLogs = JSON.parse(existingLogs); }
        if(!activeLogs.some(l => l.invoiceId === logItem.invoiceId)) {
            activeLogs.push(logItem); localStorage.setItem("islam_co_history_logs_v1", JSON.stringify(activeLogs));
        }
    }

    function downloadBillSnapshotJpgFile() {
        commitBillRecordToLocalHistoryLogs();
        const node = document.getElementById("invoicePrintCaptureTargetCanvas");
        html2canvas(node, { scale: 3, useCORS: true, backgroundColor: "#ffffff" }).then(canvas => {
            const a = document.createElement("a"); a.download = `INVOICE_${stateInvoiceRandomKey}.jpg`;
            a.href = canvas.toDataURL("image/jpeg", 1.0); a.click();
        });
    }

    function commitRecordAndTransmitWhatsAppMessage() {
        const outletIdVal = document.getElementById("inputClientRegistrySearchKey").value.trim();
        const outletNameVal = document.getElementById("fieldUiOutletName").value.trim();
        if (!outletIdVal || !outletNameVal || localActiveSalesBasketArray.length === 0) return alert("System state validation fail.");
        commitBillRecordToLocalHistoryLogs();
        let summary = localActiveSalesBasketArray.map(p => `${p.packName} (Qty: ${p.quantity})`).join(", ");
        let params = new URLSearchParams();
        params.append("outletId", outletIdVal); params.append("outletName", outletNameVal); params.append("productsName", summary); 
        params.append("bookerName", authenticatedUserBookerString); params.append("totalBill", document.getElementById("billSummaryGrandNet").innerText); params.append("invoiceKey", stateInvoiceRandomKey);

        fetch(DEPLOYED_GAS_API_ENDPOINT, { method: "POST", mode: "no-cors", body: params }).then(() => {
            let msg = `*ISLAM AND CO ORDER*\n*Invoice ID:* ${stateInvoiceRandomKey}\n*Outlet Name:* ${outletNameVal}\n-------------------\n`;
            localActiveSalesBasketArray.forEach(r => { msg += `• ${r.packName} | Qty: ${r.quantity}\n`; });
            msg += `-------------------\n*Net Bill:* Rs. ${document.getElementById("billSummaryGrandNet").innerText}`;
            window.open(`https://api.whatsapp.com/send?phone=${document.getElementById("selectWhatsAppStaffMemberNode").value}&text=${encodeURIComponent(msg)}`, "_blank");
            clearEntireActiveBillData();
        });
    }

    function openHistorySystemModalWindow() { document.getElementById("modalOverlayHistorySystem").style.display = "flex"; renderHistoryModuleViews(); }
    function closeHistorySystemModalWindow() { document.getElementById("modalOverlayHistorySystem").style.display = "none"; }

    function switchHistoryActiveTab(targetTab) {
        currentActiveHistoryTab = targetTab;
        document.getElementById("tabHistoryPickList").classList.remove("active-tab"); document.getElementById("tabHistoryPreview").classList.remove("active-tab");
        document.getElementById("panelHistoryPickList").classList.remove("active-panel"); document.getElementById("panelHistoryPreview").classList.remove("active-panel");
        if(targetTab === 'PickList') {
            document.getElementById("tabHistoryPickList").classList.add("active-tab"); document.getElementById("panelHistoryPickList").classList.add("active-panel");
        } else {
            document.getElementById("tabHistoryPreview").classList.add("active-tab"); document.getElementById("panelHistoryPreview").classList.add("active-panel");
        }
        renderHistoryModuleViews();
    }

    function renderHistoryModuleViews() {
        const fromDate = document.getElementById("historyFilterFromDate").value;
        const toDate = document.getElementById("historyFilterToDate").value;
        
        const rawLogs = localStorage.getItem("islam_co_history_logs_v1"); let allLogs = rawLogs ? JSON.parse(rawLogs) : [];
        
        let filteredLogs = allLogs.filter(l => {
            return l.date >= fromDate && l.date <= toDate;
        });

        let rangeAggregateBillSum = 0;
        filteredLogs.forEach(log => { rangeAggregateBillSum += parseFloat(log.totalNetBill || 0); });
        document.getElementById("lblRangeHistoryTotalAmount").innerText = `Total Amount In Selected Period: Rs. ${rangeAggregateBillSum.toLocaleString()}`;

        const pickContainer = document.getElementById("historyPickListContainer");
        if(filteredLogs.length === 0) {
            pickContainer.innerHTML = `<div style="text-align:center; padding:20px; color:#64748b;">No history records found for this date range.</div>`;
        } else {
            let productSummaryMap = {}; let totalCasesCount = 0; let sampleLog = filteredLogs[0];
            filteredLogs.forEach(log => {
                log.basketItems.forEach(item => {
                    if(!productSummaryMap[item.packName]) { productSummaryMap[item.packName] = 0; }
                    productSummaryMap[item.packName] += item.quantity; totalCasesCount += item.quantity;
                });
            });
            let headerMetaHtml = `<div style="border-bottom:1px dashed #000; padding-bottom:5px; margin-bottom:8px; line-height:1.4;"><strong>📅 Range:</strong> ${fromDate} To ${toDate} <br><strong>👤 Booker:</strong> ${sampleLog.bookerName}</div><div style="font-weight:bold; margin-bottom:4px; display:grid; grid-template-columns:3fr 1fr; border-bottom:1px solid #000;"><div>Product Description Name</div><div style="text-align:right;">Total Qty</div></div>`;
            let rowsHtml = "";
            for (let pName in productSummaryMap) { rowsHtml += `<div style="display:grid; grid-template-columns:3fr 1fr; padding:3px 0; border-bottom:0.5px solid #e2e8f0;"><div>${pName}</div><div style="text-align:right; font-weight:bold;">${productSummaryMap[pName]} Pcs</div></div>`; }
            let footerMetaHtml = `<div style="margin-top:10px; padding-top:5px; border-top:1px solid #000; text-align:right; font-weight:bold; font-size:13px; color:var(--brand-blue);">Total Combined Cases Loadout: ${totalCasesCount} Pcs</div>`;
            pickContainer.innerHTML = headerMetaHtml + rowsHtml + footerMetaHtml;
        }

        const tableBody = document.getElementById("historyBillPreviewTableBodyTarget"); tableBody.innerHTML = "";
        if(filteredLogs.length === 0) { tableBody.innerHTML = `<tr><td colspan="4" style="text-align:center; padding:15px; color:#64748b;">No bills generated in this range.</td></tr>`; } 
        else {
            filteredLogs.forEach(log => {
                tableBody.innerHTML += `<tr><td>${log.invoiceId}</td><td>${log.outletName} (${log.date})</td><td>Rs. ${log.totalNetBill}</td><td style="text-align:center;"><button class="btn-ui-action" style="background:var(--brand-accent); height:24px; font-size:10px; padding:0 8px;" onclick="reloadTargetBillFromHistoryToViewport('${log.invoiceId}')">Preview</button></td></tr>`;
            });
        }
    }

    function reloadTargetBillFromHistoryToViewport(invId) {
        const rawLogs = localStorage.getItem("islam_co_history_logs_v1"); if(!rawLogs) return;
        let allLogs = JSON.parse(rawLogs); let log = allLogs.find(l => l.invoiceId === invId);
        if(log) {
            localActiveSalesBasketArray = log.basketItems;
            document.getElementById("inputClientRegistrySearchKey").value = log.outletId; document.getElementById("fieldUiOutletName").value = log.outletName;
            document.getElementById("fieldUiOutletAddress").value = log.outletAddress; document.getElementById("fieldUiContactNumber").value = log.contactNumber;
            document.getElementById("fieldUiOwnerName").value = log.ownerName; document.getElementById("selectGlobalTaxAppPolicy").value = log.taxPolicy;
            stateInvoiceRandomKey = log.invoiceId; stateDispatchRandomKey = log.dispatchId; stateDriverRandomString = log.driverName; stateVehRandomString = log.vehicleNo; statePjpRandomString = log.pjpCode;
            executeCalculationsPipeline(); closeHistorySystemModalWindow(); saveCurrentBillStateToLocalMemory();
            alert(`📄 Invoice Record #${invId} loaded to active screen successfully!`);
        }
    }

    function purgeAllHistoryLogsWithConfirmation() {
        if(confirm("⚠️ Are you absolutely sure you want to completely delete all localized history records from memory?")) {
            localStorage.removeItem("islam_co_history_logs_v1"); renderHistoryModuleViews(); alert("🗑️ All history records deleted successfully!");
        }
    }

    function exportPickListToExcelFormat() {
        const fromDate = document.getElementById("historyFilterFromDate").value; const toDate = document.getElementById("historyFilterToDate").value;
        const rawLogs = localStorage.getItem("islam_co_history_logs_v1"); let allLogs = rawLogs ? JSON.parse(rawLogs) : [];
        let filteredLogs = allLogs.filter(l => l.date >= fromDate && l.date <= toDate);
        if(filteredLogs.length === 0) return alert("No items data available to export for this specific range.");
        let productSummaryMap = {}; let totalCasesCount = 0; let sampleLog = filteredLogs[0];
        filteredLogs.forEach(log => {
            log.basketItems.forEach(item => {
                if(!productSummaryMap[item.packName]) productSummaryMap[item.packName] = 0;
                productSummaryMap[item.packName] += item.quantity; totalCasesCount += item.quantity;
            });
        });
        let excelRows = ""; for (let pName in productSummaryMap) { excelRows += `<tr><td>${pName}</td><td>${productSummaryMap[pName]}</td></tr>`; }
        let excelTemplate = `<table border="1"><tr><th colspan="2" style="background:#1e40af; color:#fff; font-weight:bold;">ISLAM AND CO. - LOADOUT PICK LIST</th></tr><tr><td><b>Range:</b></td><td>${fromDate} To ${toDate}</td></tr><tr><td><b>Booker:</b></td><td>${sampleLog.bookerName}</td></tr><tr style="background:#f1f5f9; font-weight:bold;"><td>Product Name</td><td>Total Quantity (Pcs)</td></tr>${excelRows}<tr style="background:#e2e8f0; font-weight:bold;"><td>Total Combined Cases:</td><td>${totalCasesCount} Pcs</td></tr></table>`;
        const blob = new Blob([excelTemplate], { type: "application/vnd.ms-excel" }); const a = document.createElement("a");
        a.href = URL.createObjectURL(blob); a.download = `LOADOUT_RANGE_LIST_${fromDate}_TO_${toDate}.xls`; a.click();
    }

    function terminateUserSessionState() { localStorage.removeItem("islam_co_token_secure_2026"); location.reload(); }
</script>
</body>
</html>

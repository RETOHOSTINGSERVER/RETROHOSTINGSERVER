# RETROHOSTINGSERVER
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Admin Portal - EbixConsolServer</title>
    <style>
        :root {
            --primary-color: #2c3e50;
            --secondary-color: #34495e;
            --accent-color: #3498db;
            --light-color: #ecf0f1;
            --dark-color: #1a1a1a;
            --success-color: #2ecc71;
            --warning-color: #f39c12;
            --danger-color: #e74c3c;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background-color: var(--dark-color);
            color: var(--light-color);
            min-height: 100vh;
        }
        
        .container {
            display: flex;
            min-height: 100vh;
        }
        
        .sidebar {
            width: 250px;
            background-color: var(--primary-color);
            padding: 20px;
            box-shadow: 2px 0 5px rgba(0,0,0,0.1);
        }
        
        .main-content {
            flex: 1;
            padding: 20px;
            background-color: var(--secondary-color);
        }
        
        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding-bottom: 20px;
            border-bottom: 1px solid rgba(255,255,255,0.1);
            margin-bottom: 20px;
        }
        
        .logo {
            font-size: 24px;
            font-weight: bold;
            color: var(--accent-color);
        }
        
        .clock {
            font-size: 18px;
            background-color: var(--primary-color);
            padding: 5px 15px;
            border-radius: 20px;
        }
        
        .login-container {
            max-width: 400px;
            margin: 100px auto;
            padding: 30px;
            background-color: var(--primary-color);
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(0,0,0,0.3);
        }
        
        .login-container h2 {
            text-align: center;
            margin-bottom: 30px;
            color: var(--accent-color);
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
        }
        
        .form-group input {
            width: 100%;
            padding: 12px;
            border: 1px solid rgba(255,255,255,0.2);
            background-color: rgba(255,255,255,0.1);
            border-radius: 5px;
            color: white;
            font-size: 16px;
        }
        
        .form-group input:focus {
            outline: none;
            border-color: var(--accent-color);
        }
        
        .btn {
            display: inline-block;
            padding: 12px 24px;
            background-color: var(--accent-color);
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            font-weight: 500;
            transition: background-color 0.3s;
        }
        
        .btn:hover {
            background-color: #2980b9;
        }
        
        .btn-block {
            display: block;
            width: 100%;
        }
        
        .card {
            background-color: var(--primary-color);
            border-radius: 10px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 0 10px rgba(0,0,0,0.2);
        }
        
        .card-title {
            font-size: 20px;
            margin-bottom: 20px;
            color: var(--accent-color);
            border-bottom: 1px solid rgba(255,255,255,0.1);
            padding-bottom: 10px;
        }
        
        .form-row {
            display: flex;
            flex-wrap: wrap;
            margin: 0 -10px;
        }
        
        .form-col {
            flex: 1;
            min-width: 200px;
            padding: 0 10px;
            margin-bottom: 15px;
        }
        
        select {
            width: 100%;
            padding: 12px;
            border: 1px solid rgba(255,255,255,0.2);
            background-color: rgba(255,255,255,0.1);
            border-radius: 5px;
            color: white;
            font-size: 16px;
        }
        
        select:focus {
            outline: none;
            border-color: var(--accent-color);
        }
        
        .footer {
            text-align: center;
            margin-top: 40px;
            padding-top: 20px;
            border-top: 1px solid rgba(255,255,255,0.1);
            font-size: 14px;
            color: rgba(255,255,255,0.6);
        }
        
        .hidden {
            display: none;
        }
        
        .status-badge {
            display: inline-block;
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: bold;
        }
        
        .status-warranty {
            background-color: var(--success-color);
        }
        
        .status-out {
            background-color: var(--danger-color);
        }
        
        .status-amc {
            background-color: var(--warning-color);
        }
        
        .status-accept {
            background-color: var(--success-color);
        }
        
        .status-running {
            background-color: var(--accent-color);
        }
        
        .status-hold {
            background-color: var(--warning-color);
        }
        
        .status-holiday {
            background-color: var(--danger-color);
        }
        
        .search-container {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
        }
        
        .search-container select, .search-container input {
            flex: 1;
        }
        
        .search-container button {
            width: 100px;
        }
        
        .record-count {
            margin-bottom: 20px;
            font-size: 16px;
        }
        
        .file-upload {
            margin-bottom: 20px;
        }
        
        .file-upload label {
            display: block;
            margin-bottom: 10px;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 20px;
        }
        
        th, td {
            padding: 12px 15px;
            text-align: left;
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }
        
        th {
            background-color: rgba(0,0,0,0.2);
            font-weight: 500;
        }
        
        tr:hover {
            background-color: rgba(255,255,255,0.05);
        }
        
        .action-buttons {
            display: flex;
            gap: 10px;
            margin-top: 20px;
        }
        
        .btn-success {
            background-color: var(--success-color);
        }
        
        .btn-danger {
            background-color: var(--danger-color);
        }
        
        .btn-warning {
            background-color: var(--warning-color);
        }
        
        .user-menu {
            position: relative;
            display: inline-block;
        }
        
        .user-menu-btn {
            background-color: transparent;
            border: none;
            color: white;
            cursor: pointer;
            font-size: 16px;
            display: flex;
            align-items: center;
            gap: 5px;
        }
        
        .user-menu-dropdown {
            position: absolute;
            right: 0;
            background-color: var(--primary-color);
            min-width: 200px;
            box-shadow: 0 8px 16px rgba(0,0,0,0.2);
            z-index: 1;
            border-radius: 5px;
            overflow: hidden;
            display: none;
        }
        
        .user-menu:hover .user-menu-dropdown {
            display: block;
        }
        
        .user-menu-dropdown a {
            color: white;
            padding: 12px 16px;
            text-decoration: none;
            display: block;
            transition: background-color 0.3s;
        }
        
        .user-menu-dropdown a:hover {
            background-color: rgba(255,255,255,0.1);
        }
    </style>
</head>
<body>
    <!-- Login Page -->
    <div id="login-page" class="login-container">
        <h2>Admin Login</h2>
        <form id="login-form">
            <div class="form-group">
                <label for="username">Username</label>
                <input type="text" id="username" placeholder="Enter username" required>
            </div>
            <div class="form-group">
                <label for="password">Password</label>
                <input type="password" id="password" placeholder="Enter password" required>
            </div>
            <button type="submit" class="btn btn-block">Login</button>
        </form>
    </div>
    
    <!-- Main Portal (Hidden Initially) -->
    <div id="admin-portal" class="container hidden">
        <div class="sidebar">
            <div class="logo">EbixConsolServer</div>
            <div style="margin-top: 40px;">
                <div style="padding: 10px; background-color: rgba(255,255,255,0.1); border-radius: 5px; margin-bottom: 10px;">
                    Welcome, <strong>eraj12</strong>
                </div>
                <div style="margin-top: 20px;">
                    <div style="padding: 10px; cursor: pointer; border-radius: 5px;" onclick="showSection('machine-info')">Machine Information</div>
                    <div style="padding: 10px; cursor: pointer; border-radius: 5px;" onclick="showSection('customer-info')">Customer Information</div>
                    <div style="padding: 10px; cursor: pointer; border-radius: 5px;" onclick="showSection('search-records')">Search Records</div>
                    <div style="padding: 10px; cursor: pointer; border-radius: 5px;" onclick="showSection('upload-section')">Upload Files</div>
                    <div style="padding: 10px; cursor: pointer; border-radius: 5px;" onclick="showSection('view-records')">View Records</div>
                    <div style="padding: 10px; cursor: pointer; border-radius: 5px;" onclick="showSection('reports')">Reports</div>
                    <div style="padding: 10px; cursor: pointer; border-radius: 5px;" onclick="showSection('user-settings')">User Settings</div>
                </div>
            </div>
            <div style="position: absolute; bottom: 20px; left: 20px; right: 20px; font-size: 12px; color: rgba(255,255,255,0.5);">
                All Rights Reserved And Developed By Dev Makwana EBIXCONSOLSERVER 2025
            </div>
        </div>
        
        <div class="main-content">
            <div class="header">
                <h1 id="section-title">Admin Portal</h1>
                <div class="clock" id="live-clock">Loading...</div>
                <div class="user-menu">
                    <button class="user-menu-btn">
                        eraj12 <span>▼</span>
                    </button>
                    <div class="user-menu-dropdown">
                        <a href="#" onclick="showSection('user-settings')">Update Profile</a>
                        <a href="#" onclick="logout()">Logout</a>
                    </div>
                </div>
            </div>
            
            <!-- Machine Information Section -->
            <div id="machine-info-section" class="hidden">
                <div class="card">
                    <h2 class="card-title">Machine Information</h2>
                    <form id="machine-form">
                        <div class="form-row">
                            <div class="form-col">
                                <label for="machine-name">Machine Name</label>
                                <input type="text" id="machine-name" placeholder="Enter machine name">
                            </div>
                            <div class="form-col">
                                <label for="machine-serial">Machine Serial Number</label>
                                <input type="text" id="machine-serial" placeholder="Enter serial number">
                            </div>
                        </div>
                        <button type="submit" class="btn">Save Machine Info</button>
                    </form>
                </div>
                
                <div class="card">
                    <h2 class="card-title">Customer Information</h2>
                    <form id="customer-form">
                        <div class="form-row">
                            <div class="form-col">
                                <label for="customer-number">Customer Number</label>
                                <input type="text" id="customer-number" placeholder="Enter customer number">
                            </div>
                            <div class="form-col">
                                <label for="customer-name">Customer Name</label>
                                <input type="text" id="customer-name" placeholder="Enter customer name">
                            </div>
                        </div>
                        <div class="form-row">
                            <div class="form-col">
                                <label for="customer-surname">Customer Surname</label>
                                <input type="text" id="customer-surname" placeholder="Enter customer surname">
                            </div>
                            <div class="form-col">
                                <label for="customer-email">Email Address</label>
                                <input type="email" id="customer-email" placeholder="Enter email address">
                            </div>
                        </div>
                        <div class="form-row">
                            <div class="form-col">
                                <label for="customer-city">City/Village</label>
                                <input type="text" id="customer-city" placeholder="Enter city/village">
                            </div>
                            <div class="form-col">
                                <label for="customer-pincode">PIN Code</label>
                                <input type="text" id="customer-pincode" placeholder="Enter PIN code">
                            </div>
                        </div>
                        <div class="form-row">
                            <div class="form-col">
                                <label for="customer-state">State</label>
                                <input type="text" id="customer-state" placeholder="Enter state">
                            </div>
                            <div class="form-col">
                                <label for="customer-country">Country</label>
                                <input type="text" id="customer-country" placeholder="Enter country" value="India">
                            </div>
                        </div>
                        
                        <div class="form-row">
                            <div class="form-col">
                                <label for="warranty-status">Machine Status</label>
                                <select id="warranty-status">
                                    <option value="warranty">Under Warranty</option>
                                    <option value="out">Out of Warranty</option>
                                    <option value="amc">Under AMC</option>
                                </select>
                            </div>
                            <div class="form-col">
                                <label for="record-status">Record Position</label>
                                <select id="record-status">
                                    <option value="accept">Accepted</option>
                                    <option value="running">Running</option>
                                    <option value="holiday">Public Holiday</option>
                                    <option value="hold">On Hold</option>
                                </select>
                            </div>
                        </div>
                        
                        <div class="form-row">
                            <div class="form-col">
                                <label for="total-records">Total Records</label>
                                <input type="number" id="total-records" placeholder="Enter total records">
                            </div>
                        </div>
                        
                        <button type="submit" class="btn">Save Customer Info</button>
                    </form>
                </div>
            </div>
            
            <!-- Search Records Section -->
            <div id="search-records-section" class="hidden">
                <div class="card">
                    <h2 class="card-title">Search Records</h2>
                    <div class="search-container">
                        <select id="search-criteria">
                            <option value="all">All Records</option>
                            <option value="accept">Accepted</option>
                            <option value="running">Running</option>
                            <option value="holiday">Public Holiday</option>
                            <option value="hold">On Hold</option>
                        </select>
                        <input type="text" id="search-query" placeholder="Search by name or serial...">
                        <button class="btn" onclick="searchRecords()">Search</button>
                    </div>
                    
                    <div class="record-count" id="record-count">Total records found: 0</div>
                    
                    <table id="search-results">
                        <thead>
                            <tr>
                                <th>Machine Name</th>
                                <th>Serial No.</th>
                                <th>Customer Name</th>
                                <th>Status</th>
                                <th>Position</th>
                                <th>Actions</th>
                            </tr>
                        </thead>
                        <tbody>
                            <!-- Results will be populated here -->
                        </tbody>
                    </table>
                </div>
            </div>
            
            <!-- Upload Section -->
            <div id="upload-section-section" class="hidden">
                <div class="card">
                    <h2 class="card-title">Upload Files</h2>
                    <div class="file-upload">
                        <label for="image-upload">Upload Image</label>
                        <input type="file" id="image-upload" accept="image/*">
                    </div>
                    <div class="file-upload">
                        <label for="zip-upload">Upload ZIP File</label>
                        <input type="file" id="zip-upload" accept=".zip,.rar">
                    </div>
                    <button class="btn">Save Uploads</button>
                </div>
            </div>
            
            <!-- View Records Section -->
            <div id="view-records-section" class="hidden">
                <div class="card">
                    <h2 class="card-title">View Records</h2>
                    <div class="search-container">
                        <input type="text" id="record-search" placeholder="Search records...">
                        <button class="btn" onclick="filterRecords()">Filter</button>
                    </div>
                    
                    <table id="records-table">
                        <thead>
                            <tr>
                                <th>ID</th>
                                <th>Machine</th>
                                <th>Customer</th>
                                <th>Status</th>
                                <th>Created</th>
                                <th>Updated</th>
                                <th>Actions</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>1001</td>
                                <td>Printer XYZ / SN12345</td>
                                <td>John Doe</td>
                                <td><span class="status-badge status-warranty">Warranty</span></td>
                                <td>2025-01-15 10:30</td>
                                <td>2025-03-10 14:45</td>
                                <td>
                                    <button class="btn" style="padding: 5px 10px; font-size: 12px;">View</button>
                                </td>
                            </tr>
                            <tr>
                                <td>1002</td>
                                <td>Scanner ABC / SN67890</td>
                                <td>Jane Smith</td>
                                <td><span class="status-badge status-out">Out of Warranty</span></td>
                                <td>2024-11-20 09:15</td>
                                <td>2025-02-28 16:20</td>
                                <td>
                                    <button class="btn" style="padding: 5px 10px; font-size: 12px;">View</button>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                    
                    <div class="action-buttons">
                        <button class="btn btn-success">Print Report</button>
                        <button class="btn btn-warning">Export Data</button>
                    </div>
                </div>
                
                <div class="card">
                    <h2 class="card-title">Remarks</h2>
                    <div class="form-row">
                        <div class="form-col">
                            <label for="customer-remark">Customer Remark</label>
                            <textarea id="customer-remark" rows="3" style="width: 100%; padding: 10px; background-color: rgba(255,255,255,0.1); border: 1px solid rgba(255,255,255,0.2); color: white; border-radius: 5px;"></textarea>
                        </div>
                        <div class="form-col">
                            <label for="part-remark">Part Stock Remark</label>
                            <textarea id="part-remark" rows="3" style="width: 100%; padding: 10px; background-color: rgba(255,255,255,0.1); border: 1px solid rgba(255,255,255,0.2); color: white; border-radius: 5px;"></textarea>
                        </div>
                    </div>
                    <button class="btn">Save Remarks</button>
                </div>
            </div>
            
            <!-- Reports Section -->
            <div id="reports-section" class="hidden">
                <div class="card">
                    <h2 class="card-title">Reports</h2>
                    <div style="margin-bottom: 20px;">
                        <button class="btn">Generate Daily Report</button>
                        <button class="btn" style="margin-left: 10px;">Generate Monthly Report</button>
                    </div>
                    <div id="report-content" style="min-height: 300px; border: 1px dashed rgba(255,255,255,0.2); padding: 20px; border-radius: 5px;">
                        <p>Report content will appear here after generation.</p>
                    </div>
                    <div style="margin-top: 20px;">
                        <button class="btn btn-success">Print Report</button>
                        <button class="btn" style="margin-left: 10px;">Export as PDF</button>
                        <button class="btn" style="margin-left: 10px;">Export as Excel</button>
                    </div>
                </div>
            </div>
            
            <!-- User Settings Section -->
            <div id="user-settings-section" class="hidden">
                <div class="card">
                    <h2 class="card-title">User Settings</h2>
                    <form id="user-settings-form">
                        <div class="form-row">
                            <div class="form-col">
                                <label for="current-username">Current Username</label>
                                <input type="text" id="current-username" value="eraj12" readonly>
                            </div>
                            <div class="form-col">
                                <label for="new-username">New Username</label>
                                <input type="text" id="new-username" placeholder="Enter new username">
                            </div>
                        </div>
                        <div class="form-row">
                            <div class="form-col">
                                <label for="current-password">Current Password</label>
                                <input type="password" id="current-password" placeholder="Enter current password">
                            </div>
                            <div class="form-col">
                                <label for="new-password">New Password</label>
                                <input type="password" id="new-password" placeholder="Enter new password">
                            </div>
                        </div>
                        <div class="form-row">
                            <div class="form-col">
                                <label for="confirm-password">Confirm New Password</label>
                                <input type="password" id="confirm-password" placeholder="Confirm new password">
                            </div>
                        </div>
                        <button type="submit" class="btn">Update Profile</button>
                    </form>
                </div>
            </div>
            
            <div class="footer">
                All Rights Reserved And Developed By Dev Makwana EBIXCONSOLSERVER 2025
            </div>
        </div>
    </div>

    <script>
        // Login functionality
        document.getElementById('login-form').addEventListener('submit', function(e) {
            e.preventDefault();
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            
            if(username === 'eraj12' && password === '12345') {
                document.getElementById('login-page').classList.add('hidden');
                document.getElementById('admin-portal').classList.remove('hidden');
                showSection('machine-info');
                updateClock();
                setInterval(updateClock, 1000);
            } else {
                alert('Invalid username or password');
            }
        });
        
        // Logout functionality
        function logout() {
            document.getElementById('admin-portal').classList.add('hidden');
            document.getElementById('login-page').classList.remove('hidden');
            document.getElementById('username').value = '';
            document.getElementById('password').value = '';
        }
        
        // Show section
        function showSection(sectionId) {
            // Hide all sections
            document.querySelectorAll('[id$="-section"]').forEach(section => {
                section.classList.add('hidden');
            });
            
            // Show selected section
            document.getElementById(sectionId + '-section').classList.remove('hidden');
            
            // Update section title
            const titles = {
                'machine-info': 'Machine & Customer Information',
                'search-records': 'Search Records',
                'upload-section': 'Upload Files',
                'view-records': 'View Records',
                'reports': 'Reports',
                'user-settings': 'User Settings'
            };
            document.getElementById('section-title').textContent = titles[sectionId] || 'Admin Portal';
        }
        
        // Live clock
        function updateClock() {
            const now = new Date();
            const options = { 
                timeZone: 'Asia/Kolkata',
                hour: '2-digit', 
                minute: '2-digit', 
                second: '2-digit',
                hour12: true,
                day: '2-digit',
                month: '2-digit',
                year: 'numeric'
            };
            const formatter = new Intl.DateTimeFormat('en-IN', options);
            const parts = formatter.formatToParts(now);
            
            let day, month, year, hour, minute, second, dayPeriod;
            for (const part of parts) {
                switch (part.type) {
                    case 'day': day = part.value; break;
                    case 'month': month = part.value; break;
                    case 'year': year = part.value; break;
                    case 'hour': hour = part.value; break;
                    case 'minute': minute = part.value; break;
                    case 'second': second = part.value; break;
                    case 'dayPeriod': dayPeriod = part.value; break;
                }
            }
            
            document.getElementById('live-clock').textContent = 
                `${day}/${month}/${year} ${hour}:${minute}:${second} ${dayPeriod} IST`;
        }
        
        // Search records
        function searchRecords() {
            const criteria = document.getElementById('search-criteria').value;
            const query = document.getElementById('search-query').value.toLowerCase();
            
            // In a real app, this would be an API call
            // Here we're just simulating results
            const mockData = [
                {
                    machineName: 'Printer XYZ',
                    serial: 'SN12345',
                    customer: 'John Doe',
                    status: 'warranty',
                    position: 'accept'
                },
                {
                    machineName: 'Scanner ABC',
                    serial: 'SN67890',
                    customer: 'Jane Smith',
                    status: 'out',
                    position: 'hold'
                },
                {
                    machineName: 'Laptop DEF',
                    serial: 'SN24680',
                    customer: 'Robert Johnson',
                    status: 'amc',
                    position: 'running'
                }
            ];
            
            let filtered = mockData.filter(item => {
                const matchesCriteria = criteria === 'all' || item.position === criteria;
                const matchesQuery = query === '' || 
                    item.machineName.toLowerCase().includes(query) || 
                    item.serial.toLowerCase().includes(query) || 
                    item.customer.toLowerCase().includes(query);
                return matchesCriteria && matchesQuery;
            });
            
            const resultsTable = document.querySelector('#search-results tbody');
            resultsTable.innerHTML = '';
            
            filtered.forEach(item => {
                const row = document.createElement('tr');
                
                const statusClass = {
                    warranty: 'status-warranty',
                    out: 'status-out',
                    amc: 'status-amc'
                }[item.status];
                
                const positionClass = {
                    accept: 'status-accept',
                    running: 'status-running',
                    holiday: 'status-holiday',
                    hold: 'status-hold'
                }[item.position];
                
                const statusText = {
                    warranty: 'Warranty',
                    out: 'Out of Warranty',
                    amc: 'AMC'
                }[item.status];
                
                const positionText = {
                    accept: 'Accepted',
                    running: 'Running',
                    holiday: 'Public Holiday',
                    hold: 'On Hold'
                }[item.position];
                
                row.innerHTML = `
                    <td>${item.machineName}</td>
                    <td>${item.serial}</td>
                    <td>${item.customer}</td>
                    <td><span class="status-badge ${statusClass}">${statusText}</span></td>
                    <td><span class="status-badge ${positionClass}">${positionText}</span></td>
                    <td>
                        <button class="btn" style="padding: 5px 10px; font-size: 12px;">View</button>
                    </td>
                `;
                resultsTable.appendChild(row);
            });
            
            document.getElementById('record-count').textContent = `Total records found: ${filtered.length}`;
        }
        
        // Filter records (for view records section)
        function filterRecords() {
            const query = document.getElementById('record-search').value.toLowerCase();
            const rows = document.querySelectorAll('#records-table tbody tr');
            
            rows.forEach(row => {
                const text = row.textContent.toLowerCase();
                if(text.includes(query)) {
                    row.style.display = '';
                } else {
                    row.style.display = 'none';
                }
            });
        }
        
        // Initialize with login page
        document.addEventListener('DOMContentLoaded', function() {
            document.getElementById('admin-portal').classList.add('hidden');
        });
    </script>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Friends Personal Information</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 900px;
            margin: 0 auto;
            background: white;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            overflow: hidden;
        }
        
        .header {
            background: linear-gradient(135deg, #2c3e50 0%, #3498db 100%);
            color: white;
            padding: 40px 30px;
            text-align: center;
        }
        
        .header h1 {
            font-size: 2.4em;
            margin-bottom: 10px;
            font-weight: 600;
        }
        
        .form-section {
            padding: 35px;
            background: #f8f9fa;
            border-bottom: 1px solid #e9ecef;
        }
        
        .section-title {
            font-size: 1.5em;
            margin-bottom: 25px;
            color: #2c3e50;
            font-weight: 600;
        }
        
        .form-group {
            margin-bottom: 22px;
        }
        
        .form-label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: #495057;
        }
        
        .form-input {
            width: 100%;
            padding: 14px;
            border: 2px solid #dee2e6;
            border-radius: 8px;
            font-size: 16px;
            transition: border-color 0.3s;
            background: white;
        }
        
        .form-input:focus {
            border-color: #3498db;
            box-shadow: 0 0 0 3px rgba(52, 152, 219, 0.1);
            outline: none;
        }
        
        .btn-primary {
            background: linear-gradient(135deg, #3498db 0%, #2980b9 100%);
            color: white;
            border: none;
            padding: 14px 32px;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 500;
            cursor: pointer;
            transition: transform 0.2s;
        }
        
        .btn-primary:hover {
            transform: translateY(-2px);
        }
        
        .records-container {
            padding: 35px;
        }
        
        .record-card {
            background: white;
            border-left: 4px solid #3498db;
            padding: 25px;
            margin-bottom: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 12px rgba(0,0,0,0.08);
        }
        
        .record-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            padding-bottom: 15px;
            border-bottom: 1px solid #e9ecef;
        }
        
        .record-name {
            font-weight: 600;
            color: #2c3e50;
            font-size: 1.3em;
        }
        
        .record-date {
            color: #95a5a6;
            font-size: 0.9em;
        }
        
        .record-details {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-bottom: 15px;
        }
        
        .detail-item {
            margin-bottom: 10px;
        }
        
        .detail-label {
            font-weight: 500;
            color: #7f8c8d;
            margin-bottom: 3px;
        }
        
        .detail-value {
            color: #2c3e50;
            font-size: 1.1em;
        }
        
        .empty-state {
            text-align: center;
            padding: 40px;
            color: #7f8c8d;
        }
        
        @media (max-width: 768px) {
            .record-details {
                grid-template-columns: 1fr;
            }
            
            .container {
                margin: 10px;
                border-radius: 8px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>Friends Personal Information</h1>
            <p>Store and manage your friends' personal details</p>
        </div>
        
        <div class="form-section">
            <h2 class="section-title">Add Personal Information</h2>
            <form id="infoForm">
                <div class="form-group">
                    <label class="form-label" for="name">Full Name *</label>
                    <input type="text" id="name" class="form-input" placeholder="Enter full name" required>
                </div>
                
                <div class="form-group">
                    <label class="form-label" for="fatherName">Father's Name *</label>
                    <input type="text" id="fatherName" class="form-input" placeholder="Enter father's name" required>
                </div>
                
                <div class="form-group">
                    <label class="form-label" for="motherName">Mother's Name *</label>
                    <input type="text" id="motherName" class="form-input" placeholder="Enter mother's name" required>
                </div>
                
                <div class="form-group">
                    <label class="form-label" for="address">Current Address *</label>
                    <input type="text" id="address" class="form-input" placeholder="Enter complete address" required>
                </div>
                
                <div class="form-group">
                    <label class="form-label" for="phone">Mobile Number</label>
                    <input type="tel" id="phone" class="form-input" placeholder="Enter mobile number">
                </div>
                
                <div class="form-group">
                    <label class="form-label" for="birthdate">Date of Birth</label>
                    <input type="date" id="birthdate" class="form-input">
                </div>
                
                <div class="form-group">
                    <label class="form-label" for="education">Education</label>
                    <input type="text" id="education" class="form-input" placeholder="Enter education level">
                </div>
                
                <div class="form-group">
                    <label class="form-label" for="hobbies">Hobbies & Interests</label>
                    <input type="text" id="hobbies" class="form-input" placeholder="Enter hobbies and interests">
                </div>
                
                <button type="submit" class="btn-primary">Save Information</button>
            </form>
        </div>
        
        <div class="records-container">
            <h2 class="section-title">Saved Records</h2>
            <div id="recordsList">
                <div class="empty-state">
                    <p>No records saved yet. Add the first record!</p>
                </div>
            </div>
        </div>
    </div>

    <script>
        document.getElementById('infoForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Collect all information
            const name = document.getElementById('name').value.trim();
            const fatherName = document.getElementById('fatherName').value.trim();
            const motherName = document.getElementById('motherName').value.trim();
            const address = document.getElementById('address').value.trim();
            const phone = document.getElementById('phone').value.trim();
            const birthdate = document.getElementById('birthdate').value;
            const education = document.getElementById('education').value.trim();
            const hobbies = document.getElementById('hobbies').value.trim();
            
            // Required fields check
            if (!name || !fatherName || !motherName || !address) {
                alert('Please fill in all required fields (Name, Father Name, Mother Name, Address).');
                return;
            }
            
            const date = new Date().toLocaleDateString('en-US', {
                year: 'numeric',
                month: 'long',
                day: 'numeric',
                hour: '2-digit',
                minute: '2-digit'
            });
            
            const recordsList = document.getElementById('recordsList');
            
            // Remove empty state
            if (recordsList.querySelector('.empty-state')) {
                recordsList.innerHTML = '';
            }
            
            // Create new record card
            const recordCard = document.createElement('div');
            recordCard.className = 'record-card';
            recordCard.innerHTML = `
                <div class="record-header">
                    <span class="record-name">${name}</span>
                    <span class="record-date">${date}</span>
                </div>
                <div class="record-details">
                    <div class="detail-item">
                        <div class="detail-label">Father's Name</div>
                        <div class="detail-value">${fatherName}</div>
                    </div>
                    <div class="detail-item">
                        <div class="detail-label">Mother's Name</div>
                        <div class="detail-value">${motherName}</div>
                    </div>
                    <div class="detail-item">
                        <div class="detail-label">Address</div>
                        <div class="detail-value">${address}</div>
                    </div>
                    <div class="detail-item">
                        <div class="detail-label">Mobile</div>
                        <div class="detail-value">${phone || 'Not provided'}</div>
                    </div>
                    <div class="detail-item">
                        <div class="detail-label">Date of Birth</div>
                        <div class="detail-value">${birthdate || 'Not provided'}</div>
                    </div>
                    <div class="detail-item">
                        <div class="detail-label">Education</div>
                        <div class="detail-value">${education || 'Not provided'}</div>
                    </div>
                    <div class="detail-item">
                        <div class="detail-label">Hobbies</div>
                        <div class="detail-value">${hobbies || 'Not provided'}</div>
                    </div>
                </div>
            `;
            
            recordsList.prepend(recordCard);
            document.getElementById('infoForm').reset();
            alert('Information saved successfully!');
        });
    </script>
</body>
</html>

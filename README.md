<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>D365 find me tool</title>
  <style>
    .container {
    position: fixed;   /* Changed the code from before, is this ok*/
    bottom: 40%;           /* Vertically center the container - top and bottom work, which is best? */
    left: 50%;          /* Horizontally center the container - is it always left? */
    transform: translate(-50%, -50%); /* Adjust the position so the element is centered correctly - chat gpt notes, please explain */
    padding-bottom: 8px; /* How do I make the responses also be in the middle of the page? When I move it across the page, it deletes the top of the box */
} /* Why do the links except for my email come up in purple? Is it because I clicked them before I put them in? */
  </style>
  <title>Mizkan logo</title>
    <style>
        body {
            margin: 0;
            height: 100vh;
        }
        .image-container {
            position: absolute; /* Help here pls how do I make it move across the screen */
            top: 0;
            right: 0;
            margin: 20px;
        }
        img {
            width: 400px; 
            height: auto;
        }
    </style>
</head>
<body>
<div class="image-container">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/ea/Mizkan_company_logo.svg/2560px-Mizkan_company_logo.svg.png" alt="Top Right Image">
    </div>
  <div id="responseContainer"></div>

  <div class="container">
    <select id="responseDropdown" onchange="addResponse()">
      <option value="default">Select an option</option>
      <option value="response1">Send me the vendor setup form link</option>
      <option value="response2">Send me the employee setup form link</option>
      <option value="response3">How do I set up a vendor on D365/the MDM</option>
      <option value="response4">Link to D365 instructions hub</option>
      <option value="response5">Other query</option>
    </select>
  </div>

  <script>
    function addResponse() {
      const dropdown = document.getElementById('responseDropdown');
      const responseContainer = document.getElementById('responseContainer');
      const value = dropdown.value;
      
      const responseHtmls = {
      	'response1': '<a href="https://forms.office.com/pages/responsepage.aspx?id=WhJYo0IRlkqc7MuWtRgoD3sct079UOpDqYUufHcxtMVURjAwOEZJRU05Nk5aTlZDWEgzNEg5TDlWRyQlQCN0PWcu&route=shorturl!" target="_blank">Vendor form link</a/>',
      	'response2': '<a href="https://nakanofoods.sharepoint.com/:w:/r/sites/Nemo-Proc-SC-Workspace-Procurement/_layouts/15/Doc.aspx?sourcedoc=%7BC9BFE466-DABD-4445-B237-201A701E8534%7D&file=D365%20Employee%20Set%20Up%20Form.doc&action=default&mobileredirect=true" target="_blank">Employee bank details form</a>',
      	'response3': '<a href="https://nakanofoods.sharepoint.com/:w:/r/sites/Nemo-Proc-SC-Workspace-Procurement/_layouts/15/Doc.aspx?sourcedoc=%7B8C75ED4E-F7BF-4257-8056-C8C4E19B2E43%7D&file=MDM%20Vendor%20Set%20Up%20Process%20-%20For%20Employees.docx&action=default&mobileredirect=true" target="_blank">Vendor Setup Instructions for D365 and the MDM</a>',
      	'response4': '<a href="https://nakanofoods.sharepoint.com/sites/D365Hub" target="_blank">Employee bank details form</a>',
      	'response5': '<a href="mailto:lizzi.burford@mizkan.co.uk" target="_blank">Email Lizzi</a>',
      }
      
      const htmlElementToDisplay = responseHtmls[value];
      if (htmlElementToDisplay !== undefined) {
        var responseBubble = document.createElement('div');
        responseBubble.innerHTML = htmlElementToDisplay;
        responseContainer.appendChild(responseBubble);
      }
    }
  </script>

</body>
</html>

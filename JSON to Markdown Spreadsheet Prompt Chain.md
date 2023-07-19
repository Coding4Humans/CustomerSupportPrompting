## Preface
After a few itterations with small changes i was able to get GPT 3.5 to format all the syntehsized JSON data into a markdown spreadsheet format. 
To ge thtis to work i had to create the first two rows as an example, explicitely request that it replace "," with linebreak, remove the quotation marks, and manually correct the weird formatting from the copied responses from the various LLMs. 

linebreak is explicitely used to enable a clean and readable paste into google sheets

Here is the prompt chain.
Since the prompts are large i'll be separating them with headers

### Prompt
```
Help me format JSON files into a markdown spreadsheet by formatting the JSON data as plain text and delineate the entire JSON block with | to separate the cells.
Each JSON data structure should be in one cell.
I will give you the JSON for each column separately with the name of the column first.

Here is an example with the correct header and first two rows converting the JSON data to markdown format, removing all “ and using <br> to replace commas and line breaks as necessary to keep the JSON data in one cell and organizing the cells by correct row and column
|GPT 3.5| GPT 4|Claude-Instant|Claude-Instant-100k|Claude-2-100k|
|-----------|-------------|----------------|---------------------------|-------------------|
|account: john.doe@madeBy.AI<br>id: 98765432<br>primary: Billing<br>secondary: Cancel Subscription|account: john.doe@madeBy.AI<br>id: 12345678<br>primary: Billing<br>secondary: Cancel Subscription|account: john.doe@madeBy.AI<br>id: 34567321<br>primary: Billing<br>secondary: Cancel Subscription|john.doe@madeBy.AI: 33555668<br>primary: Billing<br>secondary: Cancel Subscription|account: john.doe@madeBy.AI<br>id: 54546785<br>primary: Billing<br>secondary: Cancel Subscription|
|account: jane.smith@madeBy.AI<br>id: 12345678<br>primary: Billing<br>secondary: Refund or Replacement|account: jane.smith@madeBy.AI<br>id: 23456789<br>primary: Billing<br>secondary: Refund or Replacement|account: jane.smith@madeBy.AI<br>id: 75567718<br>primary: Billing<br>secondary: Refund or Replacement|jane.smith@madeBy.AI: 33555664<br>primary: Billing<br>secondary: Refund or Replacement|account: jane.smith@madeBy.AI<br>id: 12092763<br>primary: Billing<br>secondary: Refund or Replacement|

Please make your reply in markdown code format so that it can be copied and pasted into a .md file

Here is the data for GPT 3.5
{
"account": "john.doe@madeBy.AI",
"id": "98765432",
"primary": "Billing",
"secondary": "Cancel Subscription"
}
{
"account": "jane.smith@madeBy.AI",
"id": "12345678",
"primary": "Billing",
"secondary": "Refund or Replacement"
}
{
"account": "michael.johnson@madeBy.AI",
"id": "87654321",
"primary": "Billing",
"secondary": "Explanation for Charge"
}
{
"account": "emily.brown@madeBy.AI",
"id": "45678901",
"primary": "Billing",
"secondary": "Add or Change Payment Method"
}
{
"account": "david.wilson@madeBy.AI",
"id": "23456789",
"primary": "Technical Support",
"secondary": "General Troubleshooting"
}
{
"account": "sarah.thompson@madeBy.AI",
"id": "34567890",
"primary": "Account Management",
"secondary": "Password Reset"
}
{
"account": "samantha.carter@madeBy.AI",
"id": "56789012",
"primary": "Billing",
"secondary": "Explanation for Charge"
}
{
"account": "daniel.martinez@madeBy.AI",
"id": "78901234",
"primary": "Technical Support",
"secondary": "General Troubleshooting"
}
{
"account": "benjamin.taylor@madeBy.AI",
"id": "90817263",
"primary": "Account Management",
"secondary": "Add or Change Payment Method"
}
{
"account": "samantha.davis@madeBy.AI",
"id": "17263548",
"primary": "Billing",
"secondary": "Explanation for Charge"
}
{
"account": "john.smith@madeBy.AI",
"id": "25364798",
"primary": "Billing",
"secondary": "Refund or Replacement"
}
{
"account": "aisha.bello@madeBy.AI",
"id": "36485970",
"primary": "General Inquiry",
"secondary": "Order Status"
}
{
"account": "karen.johnson@madeBy.AI",
"id": "48597012",
"primary": "General Inquiry",
"secondary": "Order Status"
}
{
"account": "li.wei@madeBy.AI",
"id": "59608123",
"primary": "Technical Support",
"secondary": "General Troubleshooting"
}
{
"account": "emily.davis@example.com",
"id": "60719234",
"primary": "General Inquiry",
"secondary": "Speak to a Human"
}

Here is the data for GPT 4
{
"account": "john.doe@madeBy.AI",
"id": "12345678",
"primary": "Billing",
"secondary": "Cancel Subscription"
},
{
"account": "jane.smith@madeBy.AI",
"id": "23456789",
"primary": "Billing",
"secondary": "Refund or Replacement"
},
{
"account": "michael.johnson@madeBy.AI",
"id": "34567890",
"primary": "Billing",
"secondary": "Explanation for Charge"
},
{
"account": "emily.brown@madeBy.AI",
"id": "45678901",
"primary": "Billing",
"secondary": "Add or Change Payment Method"
},
{
"account": "david.wilson@madeBy.AI",
"id": "56789012",
"primary": "Technical Support",
"secondary": "General Troubleshooting"
},
{
"account": "sarah.thompson@madeBy.AI",
"id": "67890123",
"primary": "Account Management",
"secondary": "Password Reset"
},
{
"account": "samantha.carter@madeBy.AI",
"id": "78901234",
"primary": "Billing",
"secondary": "Explanation for Charge"
},
{
"account": "daniel.martinez@madeBy.AI",
"id": "89012345",
"primary": "Technical Support",
"secondary": "General Troubleshooting"
},
{
"account": "benjamin.taylor@madeBy.AI",
"id": "90123456",
"primary": "Billing",
"secondary": "Add or Change Payment Method"
},
{
"account": "samantha.davis@madeBy.AI",
"id": "01234567",
"primary": "Billing",
"secondary": "Explanation for Charge"
},
{
"account": "john.smith@madeBy.AI",
"id": "10234567",
"primary": "Billing",
"secondary": "Refund or Replacement"
},
{
"account": "aisha.bello@madeBy.AI",
"id": "11234567",
"primary": "General Inquiry",
"secondary": "Order Status"
},
{
"account": "karen.johnson@madeBy.AI",
"id": "12234567",
"primary": "Billing",
"secondary": "Refund or Replacement"
},
{
"account": "li.wei@madeBy.AI",
"id": "13234567",
"primary": "Technical Support",
"secondary": "General Troubleshooting"
},
{
"account": "emily.davis@example.com",
"id": "14234567",
"primary": "General Inquiry",
"secondary": "Speak to a Human"
}

Here is the data for Claude-Instant
{
"account": "john.doe@madeBy.AI",
"id": "34567321",
"primary": "Billing",
"secondary": "Cancel Subscription"
}
{
"account": "jane.smith@madeBy.AI",
"id": "75567718",
"primary": "Billing",
"secondary": "Refund or Replacement"
}
{
"account": "michael.johnson@madeBy.AI",
"id": "91953189",
"primary": "Billing",
"secondary": "Explanation for Charge"
}
{
"account": "emily.brown@madeBy.AI",
"id": "48888889",
"primary": "Billing",
"secondary": "Add or Change Payment Method"
}
{
"account": "david.wilson@madeBy.AI",
"id": "23324001",
"primary": "Technical Support",
"secondary": "General Troubleshooting"
}
{
"account": "sarah.thompson@madeBy.AI",
"id": "82928377",
"primary": "Account Management",
"secondary": "Password Reset"
}
{
"account": "samantha.carter@madeBy.AI",
"id": "45691354",
"primary": "Billing",
"secondary": "Explanation for Charge"
}
{
"account": "daniel.martinez@madeBy.AI",
"id": "49508683",
"primary": "Technical Support",
"secondary": "General Troubleshooting"
}
{
"account": "benjamin.taylor@madeBy.AI",
"id": "28617581",
"primary": "Account Management",
"secondary": "Add or Change Payment Method"
}
{
"account": "samantha.davis@madeBy.AI",
"id": "88277749",
"primary": "Billing",
"secondary": "Explanation for Charge"
}
{
"account": "john.smith@madeBy.AI",
"id": "72077321",
"primary": "Billing",
"secondary": "Refund or Replacement"
}
{
"account": "aisha.bello@madeBy.AI",
"id": "58074754",
"primary": "General Inquiry",
"secondary": "Order Status"
}
{
"account": "karen.johnson@madeBy.AI",
"id": "61383027",
"primary": "General Inquiry",
"secondary": "Speak to a Human"
}
{
"account": "li.wei@madeBy.AI",
"id": "59927558",
"primary": "Technical Support",
"secondary": "General Troubleshooting"
}
{
"account": "emily.davis@example.com",
"id": "16391315",
"primary": "General Inquiry",
"secondary": "General Inquiry"
}

Here is the data for Claude-instant-100k
{
"john.doe@madeBy.AI": "33555668",
"primary": "Billing",
"secondary": "Cancel Subscription"
}
{
"jane.smith@madeBy.AI": "33555664",
"primary": "Billing",
"secondary": "Refund or Replacement"
}
{
"michael.johnson@madeBy.AI": "33555667",
"primary": "Billing",
"secondary": "Explanation for Charge"
}
{
"emily.brown@madeBy.AI": "33555666",
"primary": "Billing",
"secondary":"Add or Change Payment Method"
}
{
"david.wilson@madeBy.AI": "33555660",
"primary": "Technical Support",
"secondary": "General Troubleshooting"
}
{
"sarah.thompson@madeBy.AI": "33555665",
"primary": "Account Management",
"secondary": "Password Reset"
}
{
"samantha.carter@madeBy.AI": "33555669",
"primary":"Billing",
"secondary": "Explanation for Charge"
}
{
"daniel.martinez@madeBy.AI": "33555661",
"primary":"Technical Support",
"secondary":"Device Compatibility"
}
{
"benjamin.taylor@madeBy.AI": "33555662",
"primary":"Billing",
"secondary":"Add or Change Payment Method"
}
{
"samantha.davis@madeBy.AI": "33555663",
"primary":"Billing",
"secondary":"Explanation for Charge"
}
{
"john.smith@madeBy.AI": "33555659",
"primary":"Billing",
"secondary": "Refund or Replacement"
}
{
"aisha.bello@madeBy.AI": "33555658",
"primary":"General Inquiry",
"secondary":"Order Status"
}
{
"karen.johnson@madeBy.AI": "33555657",
"primary":"General Inquiry",
"secondary":"Speak to a Human"
}
{
"li.wei@madeBy.AI": "33555656",
"primary":"Technical Support",
"secondary":"General Troubleshooting"
}
{
"emily.davis@example.com": "91679163",
"primary": "General Inquiry",
"secondary": "Product Information"
}

Here is the data for Claude-2-100k
{
"account": "john.doe@madeBy.AI",
"id": "54546785",
"primary": "Billing",
"secondary": "Cancel Subscription"
}
{
"account": "jane.smith@madeBy.AI",
"id": "12092763",
"primary": "Billing",
"secondary": "Refund or Replacement"
}
{
"account": "michael.johnson@madeBy.AI",
"id": "79045236",
"primary": "Billing",
"secondary": "Explanation for Charge"
}
{
"account": "emily.brown@madeBy.AI",
"id": "64218905",
"primary": "Billing",
"secondary": "Add or Change Payment Method"
}
{
"account": "david.wilson@madeBy.AI",
"id": "83564902",
"primary": "Technical Support",
"secondary": "General Troubleshooting"
}
{
"account": "sarah.thompson@madeBy.AI",
"id": "92741653",
"primary": "Account Management",
"secondary": "Password Reset"
}
{
"account": "samantha.carter@madeBy.AI",
"id": "10385276",
"primary": "Billing",
"secondary": "Explanation for Charge"
}
{
"account": "daniel.martinez@madeBy.AI",
"id": "56418927",
"primary": "Technical Support",
"secondary": "General Troubleshooting"
}
{
"account": "benjamin.taylor@madeBy.AI",
"id": "72349106",
"primary": "Account Management",
"secondary": "Add or Change Payment Method"
}
{
"account": "samantha.davis@madeBy.AI",
"id": "84601735",
"primary": "Billing",
"secondary": "Explanation for Charge"
}
{
"account": "john.smith@madeBy.AI",
"id": "63549218",
"primary": "Billing",
"secondary": "Refund or Replacement"
}
{
"account": "aisha.bello@madeBy.AI",
"id": "41527836",
"primary": "General Inquiry",
"secondary": "Order Status"
}
{
"account": "karen.johnson@madeBy.AI",
"id": "83745692",
"primary": "Billing",
"secondary": "Refund or Replacement"
}
{
"account": "li.wei@madeBy.AI",
"id": "29631748",
"primary": "Technical Support",
"secondary": "General Troubleshooting"
}
{
"account": "emily.davis@example.com",
"id": "56432197",
"primary": "General Inquiry",
"secondary": "Speak to a Human"
}
```

### Response
`Here is the formatted markdown code with the JSON data converted into a markdown spreadsheet:`
```markdown
| GPT 3.5 | GPT 4 | Claude-Instant | Claude-Instant-100k | Claude-2-100k |
|---------|-------|----------------|---------------------|---------------|
| account: john.doe@madeBy.AI<br>id: 98765432<br>primary: Billing<br>secondary: Cancel Subscription | account: john.doe@madeBy.AI<br>id: 12345678<br>primary: Billing<br>secondary: Cancel Subscription | account: john.doe@madeBy.AI<br>id: 34567321<br>primary: Billing<br>secondary: Cancel Subscription | john.doe@madeBy.AI: 33555668<br>primary: Billing<br>secondary: Cancel Subscription | account: john.doe@madeBy.AI<br>id: 54546785<br>primary: Billing<br>secondary: Cancel Subscription |
| account: jane.smith@madeBy.AI<br>id: 12345678<br>primary: Billing<br>secondary: Refund or Replacement | account: jane.smith@madeBy.AI<br>id: 23456789<br>primary: Billing<br>secondary: Refund or Replacement | account: jane.smith@madeBy.AI<br>id: 75567718<br>primary: Billing<br>secondary: Refund or Replacement | jane.smith@madeBy.AI: 33555664<br>primary: Billing<br>secondary: Refund or Replacement | account: jane.smith@madeBy.AI<br>id: 12092763<br>primary: Billing<br>secondary: Refund or Replacement |
| account: michael.johnson@madeBy.AI<br>id: 87654321<br>primary: Billing<br>secondary: Explanation for Charge | account: michael.johnson@madeBy.AI<br>id: 34567890<br>primary: Billing<br>secondary: Explanation for Charge | account: michael.johnson@madeBy.AI<br>id: 91953189<br>primary: Billing<br>secondary: Explanation for Charge | michael.johnson@madeBy.AI: 33555667<br>primary: Billing<br>secondary: Explanation for Charge | account: michael.johnson@madeBy.AI<br>id: 79045236<br>primary: Billing<br>secondary: Explanation for Charge |
| account: emily.brown@madeBy.AI<br>id: 45678901<br>primary: Billing<br>secondary: Add or Change Payment Method | account: emily.brown@madeBy.AI<br>id: 45678901<br>primary: Billing<br>secondary: Add or Change Payment Method | account: emily.brown@madeBy.AI<br>id: 48888889<br>primary: Billing<br>secondary: Add or Change Payment Method | emily.brown@madeBy.AI: 33555666<br>primary: Billing<br>secondary: Add or Change Payment Method | account: emily.brown@madeBy.AI<br>id: 64218905<br>primary: Billing<br>secondary: Add or Change Payment Method |
| account: david.wilson@madeBy.AI<br>id: 23456789<br>primary: Technical Support<br>secondary: General Troubleshooting | account: david.wilson@madeBy.AI<br>id: 56789012<br>primary: Technical Support<br>secondary: General Troubleshooting | account: david.wilson@madeBy.AI<br>id: 23324001<br>primary: Technical Support<br>secondary: General Troubleshooting | david.wilson@madeBy.AI: 33555660<br>primary: Technical Support<br>secondary: General Troubleshooting | account: david.wilson@madeBy.AI<br>id: 83564902<br>primary: Technical Support<br>secondary: General Troubleshooting |
| account: sarah.thompson@madeBy.AI<br>id: 34567890<br>primary: Account Management<br>secondary: Password Reset | account: sarah.thompson@madeBy.AI<br>id: 67890123<br>primary: Account Management<br>secondary: Password Reset | account: sarah.thompson@madeBy.AI<br>id: 82928377<br>primary: Account Management<br>secondary: Password Reset | sarah.thompson@madeBy.AI: 33555665<br>primary: Account Management<br>secondary: Password Reset | account: sarah.thompson@madeBy.AI<br>id: 92741653<br>primary: Account Management<br>secondary: Password Reset |
| account: samantha.carter@madeBy.AI<br>id: 56789012<br>primary: Billing<br>secondary: Explanation for Charge | account: samantha.carter@madeBy.AI<br>id: 78901234<br>primary: Billing<br>secondary: Explanation for Charge | account: samantha.carter@madeBy.AI<br>id: 45691354<br>primary: Billing<br>secondary: Explanation for Charge | samantha.carter@madeBy.AI: 33555669<br>primary: Billing<br>secondary: Explanation for Charge | account: samantha.carter@madeBy.AI<br>id: 10385276<br>primary: Billing<br>secondary: Explanation for Charge |
| account: daniel.martinez@madeBy.AI<br>id: 78901234<br>primary: Technical Support<br>secondary: General Troubleshooting | account: daniel.martinez@madeBy.AI<br>id: 89012345<br>primary: Technical Support<br>secondary: General Troubleshooting | account: daniel.martinez@madeBy.AI<br>id: 49508683<br>primary: Technical Support<br>secondary: General Troubleshooting | daniel.martinez@madeBy.AI: 33555661<br>primary: Technical Support<br>secondary: General Troubleshooting | account: daniel.martinez@madeBy.AI<br>id: 56418927<br>primary: Technical Support<br>secondary: General Troubleshooting |
| account: benjamin.taylor@madeBy.AI<br>id: 90817263<br>primary: Account Management<br>secondary: Add or Change Payment Method | account: benjamin.taylor@madeBy.AI<br>id: 90123456<br>primary: Billing<br>secondary: Add or Change Payment Method | account: benjamin.taylor@madeBy.AI<br>id: 28617581<br>primary: Account Management<br>secondary: Add or Change Payment Method | benjamin.taylor@madeBy.AI: 33555662<br>primary: Billing<br>secondary: Add or Change Payment Method | account: benjamin.taylor@madeBy.AI<br>id: 72349106<br>primary: Account Management<br>secondary: Add or Change Payment Method |
| account: samantha.davis@madeBy.AI<br>id: 17263548<br>primary: Billing<br>secondary: Explanation for Charge | account: samantha.davis@madeBy.AI<br>id: 25364798<br>primary: Billing<br>secondary: Refund or Replacement | account: samantha.davis@madeBy.AI<br>id: 88277749<br>primary: Billing<br>secondary: Explanation for Charge | samantha.davis@madeBy.AI: 33555663<br>primary: Billing<br>secondary: Explanation for Charge | account: samantha.davis@madeBy.AI<br>id: 84601735<br>primary: Billing<br>secondary: Explanation for Charge |
| account: john.smith@madeBy.AI<br>id: 25364798<br>primary: Billing<br>secondary: Refund or Replacement | account: john.smith@madeBy.AI<br>id: 10234567<br>primary: Billing<br>secondary: Refund or Replacement | account: john.smith@madeBy.AI<br>id: 72077321<br>primary: Billing<br>secondary: Refund or Replacement | john.smith@madeBy.AI: 33555659<br>primary: Billing<br>secondary: Refund or Replacement | account: john.smith@madeBy.AI<br>id: 63549218<br>primary: Billing<br>secondary: Refund or Replacement |
| account: aisha.bello@madeBy.AI<br>id: 36485970<br>primary: General Inquiry<br>secondary: Order Status | account: aisha.bello@madeBy.AI<br>id: 11234567<br>primary: General Inquiry<br>secondary: Order Status | account: aisha.bello@madeBy.AI<br>id: 58074754<br>primary: General Inquiry<br>secondary: Order Status | aisha.bello@madeBy.AI: 33555658<br>primary: General Inquiry<br>secondary: Order Status | account: aisha.bello@madeBy.AI<br>id: 41527836<br>primary: General Inquiry<br>secondary: Order Status |
| account: karen.johnson@madeBy.AI<br>id: 48597012<br>primary: General Inquiry<br>secondary: Order Status | account: karen.johnson@madeBy.AI<br>id: 12234567<br>primary: Billing<br>secondary: Refund or Replacement | account: karen.johnson@madeBy.AI<br>id: 61383027<br>primary: General Inquiry<br>secondary: Speak to a Human | karen.johnson@madeBy.AI: 33555657<br>primary: General Inquiry<br>secondary: Speak to a Human | account: karen.johnson@madeBy.AI<br>id: 83745692<br>primary: Billing<br>secondary: Refund or Replacement |
| account: li.wei@madeBy.AI<br>id: 59608123<br>primary: Technical Support<br>secondary: General Troubleshooting | account: li.wei@madeBy.AI<br>id: 13234567<br>primary: Technical Support<br>secondary: General Troubleshooting | account: li.wei@madeBy.AI<br>id: 59927558<br>primary: Technical Support<br>secondary: General Troubleshooting | li.wei@madeBy.AI: 33555656<br>primary: Technical Support<br>secondary: General Troubleshooting | account: li.wei@madeBy.AI<br>id: 29631748<br>primary: Technical Support<br>secondary: General Troubleshooting |
| account: emily.davis@example.com<br>id: 60719234<br>primary: General Inquiry<br>secondary: Speak to a Human | account: emily.davis@example.com<br>id: 14234567<br>primary: General Inquiry<br>secondary: Speak to a Human | account: emily.davis@example.com<br>id: 16391315<br>primary: General Inquiry<br>secondary: General Inquiry | emily.davis@example.com: 91679163<br>primary: General Inquiry<br>secondary: Product Information | emily.davis@example.com: 56432197<br>primary: General Inquiry<br>secondary: Speak to a Human |
```
`Please copy the above markdown code and paste it into a .md file or any markdown editor to see the formatted spreadsheet.`

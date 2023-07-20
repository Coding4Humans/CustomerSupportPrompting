## Conclusion
- Claude-instant is the winner with the most accuracy and most true-to-the-prompt results! Claude-instant-100k is second place but had a minor formatting issue in the beginning. It may need a more explicit prompt and better examples to provide the perfect responses
- Most of the formatting and extra "assistant text" could be worked out with more explicit prompts.
- Using the LLMs' APi would most likely fix the formatting issue but since i do not have access to  Claude's API i'll stick with this approach for now

## GPT 3.5
- GPT 3.5 miscategorized the request from Karen and Emily. While most of the LLMs made the same mistake, GPT 3.5's miscategorization was very far off and probably would have made the already upset customer even more upset.
- It generated a clean response without any extra fluff or comments.


## GPT 4
- GPT 4 got the most categories wrong: Samantha, Karen, and Emily.
- It generated its response in json code format which made it more difficult to copy and paste.
- It also added a "assistant" style comment before providing the response

## Claude-Instant
- Claude-Instant and Claude-Instant-100k got the most correct, only miscategorizing Emily's request.
- Unfortunately in doing so it also created a new Subcategory "General Inquiry" which could be problematic

## Claude-Instant-100k
- Claude-Instant-100k had a few issues
- While it did follow the rules for the missed category, compared to Claude-instant, it had a bit of trouble generating and formatting its reply. This could probably be fixed with API access or more explicit prompting.
- It's also the only one that failed to include the "account" key which would be problematic in a JSON file.
- Side note, it's interesting to see how the ID generation made all very similar IDs

## Claude-2-100k
- Claude-2-100k performed second best in this test due to its general accuracy and how it formatted its reply. 
- It miscategorized Karen and Emily's request. Most other LLMs made the same mistakes.
- It also added extra "assistant comments" to its reply which I feel means it would need more direct and explicit instructions that Claude-instant and GPT 3.5 did not need. 

## About the misscategorized customer requests
### Karen:
- While "Refund or replacement" provided by GPT 4 and Claude-2 is correct, due to the tone of the customer request they should be directed to a human to help diffuse and potentially save the customer.
### Emily
- The request is very brief but all LLMs still managed to miscategorize this one.
- The result should be general troubleshooting since it is a simple website issue. 

##The Results
![results](https://github.com/Coding4Humans/CustomerSupportPrompting/assets/36489846/40d0989f-f98f-40cd-aabc-3197c7dbd973)
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

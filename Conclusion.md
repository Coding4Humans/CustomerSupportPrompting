## Conclusion
- Claude-instant is the winner with the most accuracy and most true-to-the-prompt results! Claude-instant-100k is second place but had a minor formatting issue in the beginning. It may need a more explicite prompt and better examples to provide the perfect responses
- Most of the formatting and extra "assistant text" could be worked out with more explicite prompts.
- Using the LLMs' APi would most likely fix the formatting issue but since i do not have access to  Claude's API i'll stick with this approach for now


## GPT 3.5
- GPT 3.5 miscatagorized the request from Karen and Emily. While most of the LLMs made the same mistake, GPT 3.5's miscategorization was very far off and probably would have made the already upset customer even more upset.
- It generated a clean response without any extra fluff or comments.


## GPT 4
- GPT 4 got the most catagories wrong: Samantha, Karen, and Emily.
- It generated it's respopnse injscon code format which made it more difficult to copy and paste.
- It also added a "assistant" style comment before providing the response

## Claude-Instant
- Claude-Instant and Claude-Instant-100k got the most correct, only miscategorizing Emily's request.
- Unfortunantly in doing so it also created a new Subcatagory "General Inquiry" which could be problematic


## Claude-Instant-100k
- Claude-Instant-100k did second best, only misscategorizing Emily's request.
- While it did follow the rules for the missed category, compared to Claude-instant, it had a bit of trouble generating and formatting it's reply. This could probably be fixed with API access or more explicite prompting. 
- Side note, it's interesting to see how the ID generation made all very similar IDs

## Claude-2-100k
- it miscategorized karen and Emily's request. Most other LLMs made the same mistakes.
- however, because it also added extra "assistant comments" to its reply i feel it would need more direct and explicite instructions that Calude-instant and GPT 3.5 did not need. 
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
| account: john.doe@madeBy.AI\nid: 98765432\nprimary: Billing\nsecondary: Cancel Subscription | account: john.doe@madeBy.AI\nid: 12345678\nprimary: Billing\nsecondary: Cancel Subscription | account: john.doe@madeBy.AI\nid: 34567321\nprimary: Billing\nsecondary: Cancel Subscription | john.doe@madeBy.AI: 33555668\nprimary: Billing\nsecondary: Cancel Subscription | account: john.doe@madeBy.AI\nid: 54546785\nprimary: Billing\nsecondary: Cancel Subscription |
| account: jane.smith@madeBy.AI\nid: 12345678\nprimary: Billing\nsecondary: Refund or Replacement | account: jane.smith@madeBy.AI\nid: 23456789\nprimary: Billing\nsecondary: Refund or Replacement | account: jane.smith@madeBy.AI\nid: 75567718\nprimary: Billing\nsecondary: Refund or Replacement | jane.smith@madeBy.AI: 33555664\nprimary: Billing\nsecondary: Refund or Replacement | account: jane.smith@madeBy.AI\nid: 12092763\nprimary: Billing\nsecondary: Refund or Replacement |
| account: michael.johnson@madeBy.AI\nid: 87654321\nprimary: Billing\nsecondary: Explanation for Charge | account: michael.johnson@madeBy.AI\nid: 34567890\nprimary: Billing\nsecondary: Explanation for Charge | account: michael.johnson@madeBy.AI\nid: 91953189\nprimary: Billing\nsecondary: Explanation for Charge | michael.johnson@madeBy.AI: 33555667\nprimary: Billing\nsecondary: Explanation for Charge | account: michael.johnson@madeBy.AI\nid: 79045236\nprimary: Billing\nsecondary: Explanation for Charge |
| account: emily.brown@madeBy.AI\nid: 45678901\nprimary: Billing\nsecondary: Add or Change Payment Method | account: emily.brown@madeBy.AI\nid: 45678901\nprimary: Billing\nsecondary: Add or Change Payment Method | account: emily.brown@madeBy.AI\nid: 48888889\nprimary: Billing\nsecondary: Add or Change Payment Method | emily.brown@madeBy.AI: 33555666\nprimary: Billing\nsecondary: Add or Change Payment Method | account: emily.brown@madeBy.AI\nid: 64218905\nprimary: Billing\nsecondary: Add or Change Payment Method |
| account: david.wilson@madeBy.AI\nid: 23456789\nprimary: Technical Support\nsecondary: General Troubleshooting | account: david.wilson@madeBy.AI\nid: 56789012\nprimary: Technical Support\nsecondary: General Troubleshooting | account: david.wilson@madeBy.AI\nid: 23324001\nprimary: Technical Support\nsecondary: General Troubleshooting | david.wilson@madeBy.AI: 33555660\nprimary: Technical Support\nsecondary: General Troubleshooting | account: david.wilson@madeBy.AI\nid: 83564902\nprimary: Technical Support\nsecondary: General Troubleshooting |
| account: sarah.thompson@madeBy.AI\nid: 34567890\nprimary: Account Management\nsecondary: Password Reset | account: sarah.thompson@madeBy.AI\nid: 67890123\nprimary: Account Management\nsecondary: Password Reset | account: sarah.thompson@madeBy.AI\nid: 82928377\nprimary: Account Management\nsecondary: Password Reset | sarah.thompson@madeBy.AI: 33555665\nprimary: Account Management\nsecondary: Password Reset | account: sarah.thompson@madeBy.AI\nid: 92741653\nprimary: Account Management\nsecondary: Password Reset |
| account: samantha.carter@madeBy.AI\nid: 56789012\nprimary: Billing\nsecondary: Explanation for Charge | account: samantha.carter@madeBy.AI\nid: 78901234\nprimary: Billing\nsecondary: Explanation for Charge | account: samantha.carter@madeBy.AI\nid: 45691354\nprimary: Billing\nsecondary: Explanation for Charge | samantha.carter@madeBy.AI: 33555669\nprimary: Billing\nsecondary: Explanation for Charge | account: samantha.carter@madeBy.AI\nid: 10385276\nprimary: Billing\nsecondary: Explanation for Charge |
| account: daniel.martinez@madeBy.AI\nid: 78901234\nprimary: Technical Support\nsecondary: General Troubleshooting | account: daniel.martinez@madeBy.AI\nid: 89012345\nprimary: Technical Support\nsecondary: General Troubleshooting | account: daniel.martinez@madeBy.AI\nid: 49508683\nprimary: Technical Support\nsecondary: General Troubleshooting | daniel.martinez@madeBy.AI: 33555661\nprimary: Technical Support\nsecondary: General Troubleshooting | account: daniel.martinez@madeBy.AI\nid: 56418927\nprimary: Technical Support\nsecondary: General Troubleshooting |
| account: benjamin.taylor@madeBy.AI\nid: 90817263\nprimary: Account Management\nsecondary: Add or Change Payment Method | account: benjamin.taylor@madeBy.AI\nid: 90123456\nprimary: Billing\nsecondary: Add or Change Payment Method | account: benjamin.taylor@madeBy.AI\nid: 28617581\nprimary: Account Management\nsecondary: Add or Change Payment Method | benjamin.taylor@madeBy.AI: 33555662\nprimary: Billing\nsecondary: Add or Change Payment Method | account: benjamin.taylor@madeBy.AI\nid: 72349106\nprimary: Account Management\nsecondary: Add or Change Payment Method |
| account: samantha.davis@madeBy.AI\nid: 17263548\nprimary: Billing\nsecondary: Explanation for Charge | account: samantha.davis@madeBy.AI\nid: 25364798\nprimary: Billing\nsecondary: Refund or Replacement | account: samantha.davis@madeBy.AI\nid: 88277749\nprimary: Billing\nsecondary: Explanation for Charge | samantha.davis@madeBy.AI: 33555663\nprimary: Billing\nsecondary: Explanation for Charge | account: samantha.davis@madeBy.AI\nid: 84601735\nprimary: Billing\nsecondary: Explanation for Charge |
| account: john.smith@madeBy.AI\nid: 25364798\nprimary: Billing\nsecondary: Refund or Replacement | account: john.smith@madeBy.AI\nid: 10234567\nprimary: Billing\nsecondary: Ref

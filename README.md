# AWS-Organization-for-Account-Multiple-Account-setup

1\. **Understanding the AWS organization hierarchy.**

AWS Organizations is a service offered by Amazon Web Services that enables centralized management of multiple AWS accounts and resources. It is particularly beneficial for businesses, enterprises, or any environment where managing multiple accounts across different teams or projects is required.

Imagine you're running a tech company called 'Joecloud,' which has multiple departments like Development, Operations, and Marketing. Each of these departments manages its own set of AWS resources, such as servers, databases, and storage.

Previously, you might have managed all these resources within a single AWS account, which can quickly become disorganized and pose security risks as your infrastructure grows. This is where AWS Organizations proves valuable.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-04-05/535009a7-21d1-47a2-9a11-dab88b4135c5/screenshot.jpeg?tl_px=0,0&br_px=1167,735&force_format=jpeg&q=100&width=1120.0)


2\. ### **Key Concepts and Features of AWS Organizations**

1. **Consolidated Billing**\
   AWS Organizations enables you to consolidate billing across all your AWS accounts. This allows you to manage payments from a central location, streamlining financial tracking and potentially reducing costs through volume discounts.

2. **Account Hierarchy**

   - **Root Account**: The top-level account in your organization, which has full control over all other accounts. It’s primarily used for administrative purposes, not for day-to-day operations.

   - **Member Accounts**: These are individual AWS accounts under the root account, typically used by different departments, projects, or teams to isolate workloads and resources.

3. **Organizational Units (OUs)**\
   Organizational Units let you group member accounts based on function or team structure. For example, in a company like *Joecloud*, you could create OUs for “Development,” “Operations,” and “Marketing” to reflect your organizational layout.

4. **Service Control Policies (SCPs)**\
   SCPs act as permission boundaries and can be applied at the root, OU, or account level. They define which AWS services and actions are allowed or denied, helping enforce governance, security, and compliance policies across your organization.

5. **Cross-Account Access**\
   AWS Organizations simplifies the process of granting access between accounts. For instance, if your Development team needs to interact with resources managed by the Operations team, you can securely enable that access without sharing sensitive credentials.

6. **Centralized Control**\
   With AWS Organizations, you gain a centralized view of all your AWS accounts and resources. This makes it easier to manage infrastructure, perform audits, and monitor activity across your environment from a single location.


3\. ### **Example Scenario: Using AWS Organizations at Joecloud**

Let’s imagine *Joecloud* is using AWS Organizations to manage its different departments effectively:

- **Development (Account 1):**\
  This account hosts resources like EC2 instances used for software development. An SCP (Service Control Policy) is applied to allow access to essential services such as Amazon S3, Amazon DynamoDB, and AWS Lambda.

- **Operations (Account 2):**\
  This account manages infrastructure components like Amazon RDS databases and Elastic Load Balancers. An SCP is enforced to restrict access to only the core services required for operational tasks, enhancing security and focus.

- **Marketing (Account 3):**\
  Dedicated to analytics and data insights, this account uses services like Amazon Redshift and Amazon QuickSight. An SCP ensures that only these analytics-related services are accessible, keeping the environment streamlined and secure.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-04-05/f0a49fd4-6ffc-42a5-b1cd-b7ae093bf28c/screenshot.jpeg?tl_px=0,0&br_px=1090,948&force_format=jpeg&q=100&width=1120.0)


4\. To create an AWS Organization, you must use the Root user from the Parent Account, which serves as the primary administrative account for managing your organization and its associated accounts.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-04-05/0decd668-d84b-4738-84d7-246e3c928b59/screenshot.jpeg?tl_px=0,0&br_px=1920,1080&force_format=jpeg&q=100&width=1120.0)


5\. After clicking 'Create an Organization,' you'll be taken to a dashboard where you can manage your AWS Organization. It's important to note that the Root Account and Management Account are automatically created by default

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-04-05/75c9c080-f428-465d-ab35-46ae747ff85f/user_cropped_screenshot.webp?tl_px=0,0&br_px=1920,1080&force_format=jpeg&q=100&width=1120.0)


6\. As an example, I created a Development Organizational Unit (dev-OU) to demonstrate how to structure AWS Organizations.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-04-05/302cc189-61e3-4587-9534-5306bd230a87/screenshot.jpeg?tl_px=0,0&br_px=1920,1080&force_format=jpeg&q=100&width=1120.0)


7\. Once created successfully, you will see it added to the list.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-04-05/2279b232-4110-40e2-bb86-37e2a780e967/user_cropped_screenshot.webp?tl_px=0,0&br_px=1920,1080&force_format=jpeg&q=100&width=1120.0)


8\. Next, I created an AWS account under our dev-OU to organize resources and manage permissions more effectively.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-04-05/cbf5ec57-ed17-4a08-9676-22a1ecece7ac/screenshot.jpeg?tl_px=0,0&br_px=1920,1080&force_format=jpeg&q=100&width=1120.0)


9\. This is our new dev account, created under the dev-OU for development purposes.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-04-05/a55293c4-c77e-4f2b-8ce2-1bad04197155/user_cropped_screenshot.webp?tl_px=0,0&br_px=1920,1080&force_format=jpeg&q=100&width=1120.0)


10\. Log in to our new dev account using the email address you used during the account creation process, then click 'Next.'

It’s important to note that you cannot reuse an email address when creating AWS accounts.

Next, click 'Forgot Password' to receive a password reset link via email.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-04-05/19e297c0-f302-4afb-be76-369a1ed7c10e/user_cropped_screenshot.webp?tl_px=0,0&br_px=1920,1080&force_format=jpeg&q=100&width=1120.0)


11\. Check your email and click the link sent to you, which will direct you to the dashboard.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-04-05/116d3052-307e-409d-810b-3701c17bae43/screenshot.jpeg?tl_px=0,0&br_px=901,387&force_format=jpeg&q=100&width=901)


12\. I have now accessed my dev account under the Development Organizational Unit (dev-OU).

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-04-05/92608718-b3e6-4e14-9b4e-28eed44fa7f4/screenshot.jpeg?tl_px=0,0&br_px=1920,1080&force_format=jpeg&q=100&width=1120.0)


13\. ### **Benefits and Conclusion: Simplify Your Cloud Management with AWS Organizations**

With AWS Organizations, your organization benefits from a clear separation of responsibilities—each department operates within its own AWS account, with dedicated resources and tightly controlled access. Consolidated billing simplifies financial oversight by centralizing payments across all accounts. Additionally, cross-account access enables secure collaboration, such as allowing the DevOps team in the Development account to manage infrastructure in the Operations account—without the need to share sensitive credentials.

In essence, AWS Organizations offers a structured and secure approach to managing multiple AWS accounts. It helps ensure compliance, enhances security, and optimizes resource management—making it an essential tool for growing teams and enterprises alike.


14\. ### **Final Thoughts: Empower Your Cloud Journey**

AWS Organizations is your gateway to simplified and scalable cloud management. By combining centralized billing, powerful access controls, and seamless collaboration, it empowers your organization—whether you're just getting started or managing a complex, multi-account environment.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-04-05/6644cb39-b8c4-46be-bb19-6b1877dec90d/screenshot.jpeg?tl_px=0,0&br_px=1024,1024&force_format=jpeg&q=100&width=1120.0)

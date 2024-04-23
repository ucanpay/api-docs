# User Guides

Welcome to the UCanPay User Guides! These guides are designed to help you understand and make the most out of your UCanPay integration, covering a wide range of topics from basic setup to advanced features. Whether you are a new user or looking to expand your knowledge, these guides provide step-by-step instructions and useful tips.

## Getting Started

### Quick Setup Guide

Follow our simple step-by-step guide to get up and running with UCanPay quickly.

<procedure title="Quick Setup Guide" id="quick-setup-guide-procedure">
    <step>
        <p>Sign up for an UCanPay account and obtain your API keys.</p>
    </step>
    <step>
        <p>Integrate the UCanPay API into your application by following the integration checklist.</p>
    </step>
    <step>
        <p>Configure your payment settings, including currency, payment methods, and security options.</p>
    </step>
    <step>
        <p>Test your setup using our sandbox environment to ensure everything is working as expected.</p>
    </step>
</procedure>

### Comprehensive Integration

Detailed instructions for integrating UCanPay with various platforms and languages.

<tabs>
    <tab title="Web">
        <code-block lang="html">
            <!-- Example of HTML integration -->
            <script src="ucanpay.js"></script>
            <button onclick="ucanpay.init('YOUR_API_KEY')">Pay Now</button>
        </code-block>
    </tab>
    <tab title="Mobile">
        <code-block lang="swift">
            // Example of iOS integration using Swift
            UCanPayAPI.shared.initialize(apiKey: "YOUR_API_KEY")
        </code-block>
    </tab>
</tabs>

## Advanced Features

Learn how to leverage advanced features such as recurring payments, multi-currency support, and real-time analytics.

### Recurring Payments

Setting up and managing subscriptions and recurring payments.

<collapsible>
    <title>Guide to Recurring Payments</title>
    <content>
This section provides a comprehensive guide to setting up recurring payments, including necessary API calls and best practices.
    </content>
</collapsible>

### Multi-Currency Transactions

How to accept and process payments in multiple currencies.

<collapsible default-state="expanded">
    <title>Handling Multi-Currency</title>
    <content>
Detailed steps and examples on managing multi-currency transactions to expand your global reach.
    </content>
</collapsible>

## Troubleshooting

### Common Issues and Resolutions

<collapsible>
    <title>FAQs on Common Issues</title>
    <content>
If you encounter common problems, refer to this section for troubleshooting tips and potential solutions.
    </content>
</collapsible>

## Feedback and Support

We are committed to improving your experience and appreciate your feedback.

<a href="https://ucanpay.ca/support">Contact Support</a>

Please reach out to our support team for assistance or to report any issues.

<seealso>
    <category ref="wrs">
        <a href="https://ucanpay.ca/docs/integration-checklists">Integration Checklists</a>
        <a href="https://ucanpay.ca/docs/advanced-features">Advanced Features</a>
    </category>
</seealso>

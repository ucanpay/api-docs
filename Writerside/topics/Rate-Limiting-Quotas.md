# Rate Limiting &amp; Quotas

UCanPay implements rate limiting and quotas to ensure fair usage and protect the API from abuse. This guide provides
details on our rate limiting policies and how to manage your usage quotas effectively.

## Understanding Rate Limits

Rate limits restrict the number of API requests that can be made within a specific time frame.

<procedure title="Understanding Rate Limits" id="understanding-rate-limits-procedure">
    <step>
        <p>Each API endpoint may have its own rate limit, which is measured in requests per minute (RPM).</p>
    </step>
    <step>
        <p>If you exceed the rate limit, you will receive a <code>429 Too Many Requests</code> HTTP status code.</p>
    </step>
    <step>
        <p>Review the headers of our responses to understand your rate limit status:</p>
        <code-block lang="http">
X-RateLimit-Limit: 1000
X-RateLimit-Remaining: 500
X-RateLimit-Reset: 1588400000
        </code-block>
    </step>
</procedure>

## Managing Quotas

Quotas determine the maximum number of requests that your application can make to the UCanPay API over a longer period,
typically a month.

<chapter title="Check Your Current Quota Usage" collapsible="true">
    <p>To check your current quota usage, visit your account dashboard at <a href="https://ucanpay.ca/dashboard">ucanpay.ca/dashboard</a>. Detailed usage statistics are available to help you plan and manage your application's demands.</p>
</chapter>

<chapter title="Requesting Quota Increases" collapsible="true">
    <p>If your business needs exceed the default quotas, you can request an increase by contacting our support team. Provide details about your use case and anticipated volume to support your request.</p>
</chapter>

## Best Practices for Managing Rate Limits

Implementing these best practices can help you avoid hitting rate limits and ensure smooth operation of your
applications.

### Caching

Utilize caching to reduce the number of requests to our servers. Store responses locally and reuse the data to handle
similar requests.

### Throttling

Implement client-side request throttling by spacing out API calls. Use a queue or a scheduler to manage the timing of
your requests.

### Handling 429 Responses

When you receive a 429 response, use the <code>X-RateLimit-Reset</code> header to determine when to retry your request.

## Monitoring and Alerts

Set up monitoring on your API usage to receive alerts when you are approaching your rate limits or quotas. This
proactive approach will allow you to adjust your usage patterns or request quota increases before issues arise.

<seealso>
    <category ref="wrs">
        <a href="https://ucanpay.ca/docs/api-monitoring">API Monitoring</a>
        <a href="https://ucanpay.ca/docs/alerts-setup">Setting Up Alerts</a>
    </category>
</seealso>

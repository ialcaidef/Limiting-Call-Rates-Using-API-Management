# Limiting-Call-Rates-Using-API-Management

### Limiting Call Rates Using API Management

#### Preparation Steps

This demo continues from the previous demo.

#### Demonstration Steps

1. Click **All resources** and then click **API Management service** from the previous demo.

2. In the **API MANAGEMENT** section, click **APIs**.

3. In the **All APIs** section, click **Demo Conference API**.

4. Select **All operations**.

5. In the **Inbound processing** window, click the triangle (next to the pencil) and select **Code editor**.

6. Position the cursor inside the **\<inbound\>** element.

7. In the window on the right side, under **Access restriction policies**, click **+ Limit call rate per key**.

8. Modify your **rate-limit-by-key** code (in the **\<inbound\>** element) to the following code:

   ```xml
    <rate-limit-by-key calls="2" renewal-period="60" counter-key="@(context.Subscription.Id)" />
   ```

9. Click **Save**.

10. Select **Demo Conference API**.

11. Click the **GetSessions** operation.

12. Select the **Test** tab.

13. Click **Send** two times in a row.

14. After sending the request two times, you get a **429 Too many requests** response.

15. Wait for 60 seconds and then click **Send** again. This time you should get a **200 OK** response.

16. Close all windows.

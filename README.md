# azure-pim-jit-access
Demonstration of Just-in-Time (JIT) access using Azure Privileged Identity Management (PIM) for secure role management.

# Just-in-Time (JIT) Access with Azure Privileged Identity Management (PIM)

This project demonstrates how to implement **Just-in-Time (JIT)** access for privileged roles using **Azure Privileged Identity Management (PIM)**. It's a practical scenario that follows the principle of **least privilege** to minimize security risks in cloud environments.

---

## 📘 Scenario

At **SecureCloud Inc.**, a Security Engineer needs temporary access to the **Azure Security Reader** role to investigate security alerts. However, they should not have standing access to reduce exposure risk.

---

## Requirements

- Access to the Security Reader role should be **Just-in-Time**.
- Activation must require **Multi-Factor Authentication (MFA)**.
- Users must provide a **business justification** for access.
- Access automatically **expires after 2 hours**.
- All activity must be **audited and logged**.

---

## Solution: Configuring PIM for JIT Access

### Step 1: Assign Role as "Eligible" in Azure PIM

1. Go to **Azure Portal** → **Azure AD** → **Privileged Identity Management**.
2. Navigate to **Azure AD roles** → **Roles**.
3. Search for **Security Reader** and select it.
4. Click **Add Assignments**, select your test user.
5. Set **Assignment Type** to `Eligible`.

---

### Step 2: Configure Role Activation Settings

- **Require MFA**: Enabled  
- **Require Justification**: Enabled  
- **Activation Duration**: 2 hours  

---

### Step 3: Test Role Activation

1. Sign in as the **test user**.
2. Navigate to **Azure Portal** → **PIM** → **My Roles**.
3. Find the **Security Reader** role and click **Activate**.
4. Provide a justification (e.g., _"Investigating security alerts"_).
5. Complete **MFA**.
6. Access is granted for 2 hours and **automatically revoked** afterward.

---

### Step 4: Monitor & Audit Access

- Go to **Azure AD** → **Sign-in Logs** and **PIM Activity Logs**.
- Verify the user's role activation, justification, and access expiration.

---

## Outcome

- Access is tightly controlled and time-bound.
- Admins gain visibility and control over privileged access.
- ⚙No manual intervention is needed for role deactivation.

---

## Use Cases

This project is ideal for:
- IAM Analyst portfolio projects.
- Demonstrating knowledge of Azure AD and PIM.
- Interview discussions on least privilege and access governance.

# Multi-Tenant Vendor Onboarding via ACM Policies

This repository contains the architecture and blueprints to demonstrate automated, secure, third-party vendor onboarding using Red Hat Advanced Cluster Management (ACM) integrated with an enterprise Single Sign-On (SSO) identity plane.

## Key Features Demonstrated:
* **Identity Provider (IdP) as Source of Truth:** Onboarding begins at the central authentication layer (e.g., Keycloak, Okta, Azure AD), enforcing enterprise governance across all platform tools.
* **Admin GUI-Driven Access Prep:** Platforms engineers prepare cluster permissions by executing a global find-and-replace on a single template string entirely within the ACM browser window.
* **Just-In-Time (JIT) Registry Provisioning:** Eliminates manual image registry setup; the vendor's dedicated Quay organization and user profile are automatically generated upon their first SSO login handshake.
* **Strict Tenant Console Isolation:** Customizes navigation shortcuts for external users, routing them strictly to their multi-cluster perspectives while removing default OpenShift infrastructure viewpoints.

---

## Repository Architecture

The repository remains flat, lightweight, and optimized for a clean, zero-copy-paste live demonstration flow:

```text
multi-tenant-vendor-onboarding-acm/
├── README.md                            # Documentation and Live Demo Script
├── 1-master-onboarding-policy.yaml      # Reusable Blueprint Policy (Dormant Template)
└── example-vendor-applications/         # Isolated application subfolder for vendor self-service
    ├── app-subscription-channel.yaml    # Pre-configured ACM Git Channel blueprint
    └── sample-workload-manifest.yaml    # Example workload template selectable via dropdown wizard

---
title: "SOPS: storing passwords in plain view" # "Managing DNS with OctoDNS"
description: # "DNS is a critical part of any infrastructure. It is the service that translates human-readable domain names into IP addresses that computers can understand. Managing DNS records can be a complex and error-prone process, especially in large environments with multiple domains and subdomains. OctoDNS is a tool that helps automate the management of DNS records across multiple providers and environments."
categories:
  - Tooling
tags:
  - devops
  - gitops
  - dns
  - automation
  - management
  - tooling
  - passwords
  - encryption
---
When dealing with sensitive information like passwords, it is essential to store them securely. Storing passwords in plain text is a significant security risk, as anyone with access to the file can read the passwords. In this article, we will explore some best practices for storing passwords securely and discuss some common pitfalls to avoid.

For IaC projects, one of the options we may use to store passwords securely is to use SOPS. SOPS is a tool that encrypts files using AWS KMS, GCP KMS, Azure Key Vault, PGP, or other encryption mechanisms. It allows you to store sensitive information like passwords, API keys, and other secrets in a secure and encrypted format.
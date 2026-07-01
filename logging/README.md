# Logging and Support Signals

## ✨ At A Glance

User-safe support guide for reporting failures, validation issues, unusual system behavior, and retry versus stop decisions.

## 🎨 Reader Promise

> This page should turn a frustrating failure into a useful support report: what happened, where it happened, and what the user saw.

## 🧭 How To Use This README

- Use this README when users need to gather useful support context from visible product behavior.
- Keep the guidance about what users can observe, retry, and report.
- Route observability internals and investigation steps to internal docs.

User-safe guidance for reporting failures, validation issues, and unusual system behavior in Orion Rigel.

## 📌 What Users Should Capture

- The page or workflow where the issue happened.
- The visible error or validation message.
- The approximate time of the issue.
- The collection, lead, or scenario involved, when relevant.
- Whether retrying changed the result.

## 🔁 Retry Guidance

- Retry when the issue appears temporary, such as a page refresh, interrupted upload, or short-lived network problem.
- Stop and contact support when the same action repeatedly fails, produces unexpected financial outputs, or blocks account access.

## 🛟 Public-Safe Support Language

Focus on what the user can see and share. Do not expose internal logging pipelines, observability tooling, correlation logic, or private admin investigation steps.

## 🛠️ Maintenance Notes

- Update this README when public support intake, visible error guidance, or retry language changes.
- Do not expose logging pipelines, telemetry implementation, correlation logic, or admin investigation steps.

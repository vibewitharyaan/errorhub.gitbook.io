---
icon: clock-rotate-left
---

# Changelog

{% updates format="full" %}
{% update date="2026-03-29" %}
## v1.3.2

<details>

<summary>Added</summary>

* Added `config.requireOnDuty` option to make on-duty checks optional

</details>
{% endupdate %}

{% update date="2026-01-31" %}
## v1.3.1

<details>

<summary>Fixed</summary>

* Fixed payment system failing to add money to business accounts
* Fixed displacement issues with cold drink prop animations
* Fixed cold drink emote placement issues
* Removed leftover debug command inside delivery loop

</details>

<details>

<summary>Improved</summary>

* Improved resource detection logic to prevent incorrect system selection
* Pending billing requests now clear automatically if a player disconnects

</details>

<details>

<summary>Changed</summary>

* **Files Updated:**
  * `bridge/` _(entire folder)_
  * `config/emote.lua`
  * `core/client/cl_billling.lua`
  * `core/server/sv_billling.lua`
  * `core/server/sv_delivery.lua`

</details>

<details>

<summary>Notes</summary>

* This is the final feature/improvement update for the Raycrest Restaurant Job script
* The resource is now in maintenance-only phase

</details>
{% endupdate %}
{% endupdates %}

{% updates format="full" %}
{% update date="2026-01-15" %}
## v1.2.1

<details>

<summary>Fixed</summary>

* **Script:** Fixed interaction target not working on spawn

</details>

<details>

<summary>Changed</summary>

* **Script Files Updated:**
  * Replaced `bridge/framework.lua` (no full script update required)

</details>
{% endupdate %}

{% update date="2025-12-20" %}
## v1.1.1

<details>

<summary>Fixed</summary>

* **Script:** Fixed cold drink animation not playing correctly
* **MLO:** Fixed water puddles appearing indoors during rain

</details>

<details>

<summary>Changed</summary>

* **Script Files Updated:**
  * `config/emote.lua`
* **MLO Files Updated:**
  * Updated MLO files

</details>
{% endupdate %}

{% update date="2025-12-14" %}
## v1.1.0

<details>

<summary>Fixed</summary>

* Resolved progress bar issues when using QBox framework with QB progress bar option
* Fixed animation issue when consuming food that caused players to fall out of vehicles
* Fixed hunger, thirst, and stress not updating correctly when consuming items in the QBox framework

</details>

<details>

<summary>Added</summary>

* Introduced configurable consumable behavior flags per item:
  * `canDrive`
  * `canCombat`
  * `canMove`

</details>
{% endupdate %}
{% endupdates %}

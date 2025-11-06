# Case Study — HDR Black Screen Bug  
ASUS ZenBook Duo 2024 (UX8406CA) — Windows 11  
Author: ISC — I Stay Curious  
Date: 2025-11-06  

---

## 🔍 Issue Summary (EN)

**Problem:**  
Black screen flashes or full display drop when plugging/unplugging power cable or detaching secondary screen.

**Device:**  
ASUS ZenBook Duo 2024 — Model: UX8406CA

**OS:**  
Windows 11 (fresh system, factory reset + cloud reinstall)

**Symptoms:**
- Screen goes black for 1–2 seconds when connecting power
- Same bug when detaching keyboard / using dual screen mode
- Battery indicator stuck at 5% while actually ~80%
- No hardware faults, no driver missing except ASUS System Control Interface showing "no driver installed"

**Root Cause:**  
⚠️ HDR mode enabled in Windows display settings  
→ Causes conflict with ACPI + screen controller  
→ Triggers display reset on power state change

**Fix (tested and confirmed by ISC):**
1. Open **Settings → System → Display**
2. Disable **HDR** (or Auto-HDR)
3. Reboot the laptop
4. Re-test: plug/unplug charger → ✅ no more black screen
5. Optional: HDR can be re-enabled only for video/gaming use, but not permanently

**Status:** ✅ FIXED  
**Reason:** Not hardware → software conflict caused by Windows HDR handling

---

## 🧠 Notes from ISC

- Bug only appears **after HDR has been ON for hours**
- Restarting without disabling HDR does NOT fix the issue
- Battery “5% stuck” message is a **false ACPI reading caused by the HDR glitch**
- ASUS System Control Interface having “no driver installed” is not the cause

---

## 🇫🇷 Résumé du bug (FR)

**Problème :**  
Écran noir 1–2 secondes lors du branchement / débranchement du chargeur ou retrait du clavier secondaire.

**Appareil :**  
ASUS ZenBook Duo 2024 — UX8406CA

**Système :**  
Windows 11 (réinstallation via Cloud / BIOS)

**Symptômes :**
- L’écran clignote noir à chaque changement d’alimentation
- Même bug quand on détache l’écran secondaire
- Batterie bloquée à 5% alors qu’elle est chargée à ~80%
- Aucun problème matériel, juste un bug logiciel

**Cause réelle :**  
⚠️ HDR activé dans Windows  
→ Conflit avec la gestion d’alimentation (ACPI)  
→ Forçage d’un reset d’affichage à chaque changement d’état

**Solution (testée et confirmée par ISC) :**
1. Aller dans **Paramètres → Système → Affichage**
2. Désactiver **HDR** (ou Auto-HDR)
3. Redémarrer le PC
4. Tester le branchement / débranchement → ✅ plus aucun écran noir

**Statut :** ✅ Corrigé  
**Origine du bug :** logiciel (Windows HDR), pas matériel

---

## 📌 Conclusion

✅ Problème reproductible  
✅ Fix confirmé  
✅ Aucun retour SAV nécessaire  
✅ L’erreur venait d’un conflit HDR, pas d’un défaut matériel

**Author:** ISC — I Stay Curious  

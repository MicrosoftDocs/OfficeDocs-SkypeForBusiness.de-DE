---
title: Verwalten von PIN-Richtlinien für Einwahlkonferenzen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 'Zusammenfassung: Erfahren Sie, wie Sie PIN-Richtlinien für Einwahlkonferenzen in Skype for Business Server verwalten.'
ms.openlocfilehash: d803e7d21be9743704402e2d9532fcfee413d804296cade2e56cbb875c965361
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343439"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a>Verwalten von PIN-Richtlinien für Einwahlkonferenzen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie PIN-Richtlinien für Einwahlkonferenzen in Skype for Business Server verwalten.
  
Skype for Business Server Benutzer, die über Active Directory Domain Services (AD DS)-Anmeldeinformationen in Ihrer Organisation verfügen, können mithilfe einer persönlichen Identifikationsnummer (PIN) als authentifizierte Benutzer an Einwahlkonferenzen teilnehmen. In einer PIN-Richtlinie werden die Regeln für die Funktionsweise der Einwahlkonferenz-PINs definiert.
  
 Wenn Sie dieselbe PIN-Richtlinie für Ihre gesamte Organisation einsetzen möchten, können Sie die globale PIN-Richtlinie verwenden und nach Bedarf anpassen. Die globale PIN-Richtlinie definiert die Regeln für Einwahlkonferenz-PINs auf Gesamtstrukturebene. Sie können die globale PIN-Richtlinie ändern, aber nicht löschen.
  
Sie können eine neue PIN-Richtlinie erstellen, wenn für einen Standort oder eine bestimmte Benutzergruppe eine bestimmte Richtlinie gelten soll.
  
Die PIN-Richtlinien gelten für Benutzer vom engsten bis hin zum weitesten Bereich. Wenn Sie einem Benutzer eine PIN-Richtlinie auf Benutzerebene zuweisen, erhalten diese Einstellungen Vorrang. Wenn Sie keine Benutzerrichtlinie zuweisen, gilt die PIN-Richtlinie auf Standortebene, falls vorhanden. Gelten weder Benutzer- noch Standortrichtlinien, stellt die globale PIN-Richtlinie die Standardeinstellungen bereit.
  
## <a name="view-information-about-pin-policies"></a>Anzeigen von Informationen zu PIN-Richtlinien

Sie können Informationen zu PIN-Richtlinien mithilfe Skype for Business Server Systemsteuerung oder mithilfe Skype for Business Server Verwaltungsshell anzeigen.
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a>Anzeigen von Informationen zu PIN-Richtlinien mithilfe Skype for Business Server Systemsteuerung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2.  Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **PIN-Richtlinie**.
    
4. Klicken Sie auf der Seite **"PIN-Richtlinie"** auf die PIN-Richtlinie, die Sie anzeigen möchten, klicken Sie auf **"Bearbeiten"** und dann auf **"Details anzeigen".**
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a>Anzeigen von Informationen zu PIN-Richtlinien mithilfe Skype for Business Server Verwaltungsshell

Verwenden Sie das Cmdlet **"Get-CsPinPolicy",** um Informationen zu PIN-Richtlinien anzuzeigen. Der folgende Befehl gibt beispielsweise Informationen zu einer einzelnen PIN-Richtlinie mit dem Identitätswert "site:Redmond" zurück:
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

Weitere Informationen, einschließlich einer vollständigen Syntaxbeschreibung und einer Liste von Parametern, finden Sie unter ["Get-CsPinPolicy".](/powershell/module/skype/get-cspinpolicy?view=skype-ps)
  
## <a name="modify-the-global-pin-policy"></a>Ändern der globalen PIN-Richtlinie

Sie können die globale PIN-Richtlinie mithilfe Skype for Business Server Systemsteuerung oder mithilfe Skype for Business Server Verwaltungsshell ändern.
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a>Ändern der globalen Richtlinie für Einwahlkonferenzen mithilfe Skype for Business Server Systemsteuerung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2.  Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **PIN-Richtlinie**.
    
4. Klicken Sie auf der Seite **"PIN-Richtlinie"** auf die **globale** Richtlinie, klicken Sie auf **"Bearbeiten"** und dann auf **"Details anzeigen".**
    
5. Geben Sie unter **PIN-Richtlinie bearbeiten** im Feld **PIN-Mindestlänge** die gewünschte Mindestlänge für die PIN ein, oder wählen Sie sie aus. In der Standardeinstellung beträgt die Mindestlänge fünf Ziffern.
    
6. Aktivieren Sie das Kontrollkästchen **Maximale Anmeldeversuche angeben**, um anzugeben, nach wie vielen erfolglosen Anmeldeversuchen ein Benutzer gesperrt wird. Wenn Sie diese Option nicht aktivieren, wird die maximale Anzahl von Anmeldeversuchen basierend auf der PIN-Länge automatisch festgelegt. In der Standardeinstellung wird die maximale Anzahl von Anmeldeversuchen automatisch festgelegt.
    
7. Wenn Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben** aktiviert haben, geben Sie in **Maximale Anzahl von Anmeldeversuchen** die maximale Anzahl von Anmeldeversuchen ein, die Sie zulassen möchten. Sie können auch einen Wert auswählen.
    
8. Aktivieren Sie das Kontrollkästchen **PIN-Ablauf aktivieren**, um eine PIN-Ablaufdauer festzulegen. Wenn Sie diese Option nicht aktivieren, laufen PINs nie ab. In der Standardeinstellung ist für PINs kein Ablauf festgelegt.
    
9. Wenn Sie das Kontrollkästchen **PIN-Ablauf aktivieren** aktiviert haben, geben Sie unter **PIN-Ablauf nach (Tagen)** die Anzahl von Tagen ein, nach der PINs ablaufen.
    
10. Geben Sie unter **PIN-Verlaufszähler** die Anzahl von PINs ein, die ein Benutzer erstellen muss, bevor eine PIN erneut verwendet werden kann. In der Standardeinstellung können Benutzer ihre PINs erneut verwenden.
    
11. Aktivieren Sie das Kontrollkästchen **Allgemeine Muster zulassen**, um allgemeine Muster in PINs zuzulassen, beispielsweise aufeinanderfolgende und wiederholte Zahlen. Wenn Sie diese Option nicht aktivieren, sind nur komplexe Ziffernmuster zulässig. In der Standardeinstellung dürfen nur komplexe Ziffernmuster verwendet werden.
    
    > [!IMPORTANT]
    > Aus Sicherheitsgründen empfiehlt Microsoft, keine allgemeinen Muster zuzulassen. 
  
12. Klicken Sie auf **Commit ausführen**.
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a>Ändern der globalen Pin-Richtlinie für Einwahlkonferenzen mithilfe Skype for Business Server Verwaltungsshell

Verwenden Sie das Cmdlet **"Set-CsPinPolicy",** um die globale Pin-Richtlinie für Einwahlkonferenzen zu ändern.
  
Der folgende Befehl ändert den Wert von MinPasswordLength für alle PIN-Richtlinien, die für die Verwendung in der Organisation konfiguriert sind. Hierzu ruft der Befehl zunächst das Cmdlet **"Get-CsPinPolicy"** ohne Parameter auf, um eine Auflistung aller vorhandenen PIN-Richtlinien abzurufen. Diese Auflistung wird dann an das Cmdlet **"Set-CsPinPolicy"** weitergeleitet, das den Wert der MinPasswordLength-Eigenschaft für jede Richtlinie in der Auflistung ändert:
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

Weitere Informationen, einschließlich einer vollständigen Syntaxbeschreibung und Einer Liste von Parametern, finden Sie unter ["Set-CsPinPolicy".](/powershell/module/skype/set-cspinpolicy?view=skype-ps)
  
## <a name="create-a-user-or-site-pin-policy"></a>Erstellen einer Benutzer- oder Standort-PIN-Richtlinie

Sie können eine BENUTZER- oder Standort-PIN-Richtlinie mithilfe Skype for Business Server Systemsteuerung oder mithilfe Skype for Business Server Verwaltungsshell erstellen.
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Erstellen einer Benutzer- oder Standort-PIN-Richtlinie mithilfe Skype for Business Server Systemsteuerung

1. Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2.  Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **PIN-Richtlinie**.
    
4. Klicken Sie auf der Seite **PIN-Richtlinie** auf **Neu**, und führen Sie eine der folgenden Aktionen aus:
    
   - Klicken Sie auf **Hinzufügen**, um eine Richtlinie auf Benutzerebene zu erstellen. Geben Sie im Abschnitt **Neue PIN-Richtlinie** in **Name** einen beschreibenden Namen für die Richtlinie ein.
    
   - Klicken Sie auf **Standortrichtlinie**, um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Suchfeld **Standort auswählen** einen Teil oder den gesamten Namen des Standorts ein, für den Sie eine Richtlinie erstellen möchten. Klicken Sie in der Liste der Standorte auf den gewünschten Standort, und klicken Sie auf **OK**.
    
5. Geben Sie im Feld **Beschreibung** eine Beschreibung für die PIN-Richtlinie ein.
    
6. Geben Sie im Feld **PIN-Mindestlänge** die gewünschte Mindestlänge für die PIN ein, oder wählen Sie sie aus. In der Standardeinstellung beträgt die Mindestlänge fünf Ziffern.
    
7. Aktivieren Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben**, um anzugeben, nach wie vielen erfolglosen Anmeldeversuchen ein Benutzer gesperrt wird. Wenn Sie diese Option nicht aktivieren, wird die maximale Anzahl von Anmeldeversuchen basierend auf der PIN-Länge automatisch festgelegt. In der Standardeinstellung wird die maximale Anzahl von Anmeldeversuchen automatisch festgelegt.
    
8. Wenn Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben** aktiviert haben, geben Sie in **Maximale Anzahl von Anmeldeversuchen** die maximale Anzahl von Anmeldeversuchen ein, die Sie zulassen möchten. Sie können auch einen Wert auswählen.
    
9. Aktivieren Sie das Kontrollkästchen **PIN-Ablauf aktivieren**, um eine PIN-Ablaufdauer festzulegen. Wenn Sie diese Option nicht aktivieren, laufen PINs nie ab. In der Standardeinstellung ist für PINs kein Ablauf festgelegt.
    
10. Wenn Sie das Kontrollkästchen **PIN-Ablauf aktivieren** aktiviert haben, geben Sie unter **PIN-Ablauf nach (Tagen)** die Anzahl von Tagen ein, nach der PINs ablaufen.
    
11. Geben Sie unter **PIN-Verlaufszähler** die Anzahl von PINs ein, die ein Benutzer erstellen muss, bevor eine PIN erneut verwendet werden kann. In der Standardeinstellung können Benutzer ihre PINs erneut verwenden.
    
12. Aktivieren Sie das Kontrollkästchen **Allgemeine Muster zulassen**, um allgemeine Muster in PINs zuzulassen, beispielsweise aufeinanderfolgende und wiederholte Zahlen. Wenn Sie diese Option nicht aktivieren, sind nur komplexe Ziffernmuster zulässig. In der Standardeinstellung dürfen nur komplexe Ziffernmuster verwendet werden.
    
    > [!IMPORTANT]
    > Aus Sicherheitsgründen empfiehlt Microsoft, keine allgemeinen Muster zuzulassen. 
  
13. Klicken Sie auf **Commit ausführen**.
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Erstellen einer Benutzer- oder Standort-PIN-Richtlinie mithilfe Skype for Business Server Verwaltungsshell

Verwenden Sie das Cmdlet **"New-CsPinPolicy",** um eine Pin-Richtlinie für Benutzer oder Websites zu erstellen.
  
Mit dem folgenden Befehl wird eine neue PIN-Richtlinie mit dem Identitätswert "site:Redmond" erstellt. Dieser Befehl enthält nur einen optionalen Parameter, MinPasswordLength, der verwendet wird, um die MinPasswordLength-Eigenschaft auf 7 festzulegen. Alle übrigen Richtlinieneigenschaften werden mit den Standardwerten konfiguriert.
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 Weitere Informationen, einschließlich einer vollständigen Syntaxbeschreibung und einer Liste von Parametern, finden Sie unter [New-CsPinPolicy.](/powershell/module/skype/new-cspinpolicy?view=skype-ps)
  
## <a name="modify-a-user-or-site-pin-policy"></a>Ändern einer Benutzer- oder Standort-PIN-Richtlinie

Sie können eine Benutzer- oder Standort-PIN-Richtlinie mithilfe Skype for Business Server Systemsteuerung oder mithilfe Skype for Business Server Verwaltungsshell ändern.
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Ändern einer Benutzer- oder Standort-PIN-Richtlinie mithilfe Skype for Business Server Systemsteuerung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2.  Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **PIN-Richtlinie**.
    
4. Klicken Sie auf der Seite **PIN-Richtlinie** auf die PIN-Richtlinie, die Sie ändern möchten. Klicken Sie dann auf **Bearbeiten** und anschließend auf **Details einblenden**.
    
5. Ändern Sie im Abschnitt **PIN-Richtlinie bearbeiten** eine beliebige der Richtlinieneinstellungen. Hiervon ausgenommen ist der Richtlinienname, dieser kann nicht geändert werden.
    
6. Klicken Sie auf **Commit ausführen**.
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Ändern einer Benutzer- oder Standort-PIN-Richtlinie mithilfe Skype for Business Server Verwaltungsshell

Verwenden Sie zum Ändern der PIN-Richtlinie für Einwahlkonferenzen das Cmdlet **"Set-CsPinPolicy".**
  
Mit dem folgenden Befehl wird die PIN-Richtlinie geändert, die dem Standort Redmond zugewiesen ist. In diesem Fall ändert der Befehl den Wert der MinPasswordLength-Eigenschaft in 10; das bedeutet, dass neue PINs mindestens 10 Ziffern enthalten müssen:
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

Weitere Informationen, einschließlich einer vollständigen Syntaxbeschreibung und Einer Liste von Parametern, finden Sie unter ["Set-CsPinPolicy".](/powershell/module/skype/set-cspinpolicy?view=skype-ps)
  
## <a name="delete-a-user-or-site-pin-policy"></a>Löschen einer Benutzer- oder Standort-PIN-Richtlinie

Sie können eine Benutzer- oder Standort-PIN-Richtlinie mithilfe Skype for Business Server Systemsteuerung oder mithilfe Skype for Business Server Verwaltungsshell löschen.
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Löschen einer Benutzer- oder Standort-PIN-Richtlinie mithilfe Skype for Business Server Systemsteuerung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2.  Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **PIN-Richtlinie**.
    
4. Klicken Sie auf der Seite **"PIN-Richtlinie"** auf die PIN-Richtlinie, die Sie ändern möchten, klicken Sie auf **"Bearbeiten"** und dann auf **"Löschen".**
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Löschen einer Benutzer- oder Standort-PIN-Richtlinie mithilfe Skype for Business Server Verwaltungsshell

Verwenden Sie das Cmdlet **"Remove-CsPinPolicy",** um eine Pin-Richtlinie eines Benutzers oder einer Website zu löschen.
  
Mit dem folgenden Befehl werden alle PIN-Richtlinien entfernt, die auf Standortebene konfiguriert wurden. Verwenden Sie dazu das Cmdlet **"Get-CsPinPolicy"** zusammen mit dem Parameter "Filter", um eine Auflistung aller Richtlinien zurückzugeben, deren Identität mit den Zeichen "site:" beginnt. Diese Auflistung wird dann an das Cmdlet **"Remove-CsPinPolicy"** weitergeleitet, das jede Richtlinie in der Auflistung löscht:
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

Weitere Informationen, einschließlich einer vollständigen Syntaxbeschreibung und einer Liste von Parametern, finden Sie unter [Remove-CsPinPolicy.](/powershell/module/skype/remove-cspinpolicy?view=skype-ps)

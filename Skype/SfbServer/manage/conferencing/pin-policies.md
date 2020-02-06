---
title: Verwalten von PIN-Richtlinien für Einwahlkonferenzen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie PIN-Richtlinien für Einwahlkonferenzen in Skype for Business Server verwalten.'
ms.openlocfilehash: 567d57edc4db5bae87653d8d3e11e44054efc0cd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818476"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a>Verwalten von PIN-Richtlinien für Einwahlkonferenzen in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie PIN-Richtlinien für Einwahlkonferenzen in Skype for Business Server verwalten.
  
Skype for Business Server-Benutzer, die über die Active Directory-Domänendienste (AD DS)-Anmeldeinformationen in Ihrer Organisation verfügen, können mithilfe einer persönlichen Identifikationsnummer (PIN) an Einwahlkonferenzen als authentifizierte Benutzer teilnehmen. In einer PIN-Richtlinie werden die Regeln für die Funktionsweise der Einwahlkonferenz-PINs definiert.
  
 Wenn Sie dieselbe PIN-Richtlinie für Ihre gesamte Organisation einsetzen möchten, können Sie die globale PIN-Richtlinie verwenden und nach Bedarf anpassen. In der globalen PIN-Richtlinie werden die Regeln für Einwahlkonferenz-PINs auf der Gesamtstrukturebene definiert. Die globale PIN-Richtlinie kann angepasst, aber nicht verändert werden.
  
Sie können eine neue PIN-Richtlinie erstellen, wenn für einen Standort oder eine bestimmte Benutzergruppe eine bestimmte Richtlinie gelten soll.
  
Die PIN-Richtlinien gelten für Benutzer vom engsten bis hin zum weitesten Bereich. Wenn Sie einem Benutzer eine PIN-Richtlinie auf Benutzerebene zuweisen, erhalten diese Einstellungen Vorrang. Wenn Sie keine Benutzerrichtlinie zuweisen, gilt die PIN-Richtlinie auf Standortebene, falls vorhanden. Gelten weder Benutzer- noch Standortrichtlinien, stellt die globale PIN-Richtlinie die Standardeinstellungen bereit.
  
## <a name="view-information-about-pin-policies"></a>Anzeigen von Informationen über PIN-Richtlinien

Sie können Informationen zu PIN-Richtlinien über die Skype for Business Server-Systemsteuerung oder über die Skype for Business Server-Verwaltungsshell anzeigen.
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a>Anzeigen von Informationen zu PIN-Richtlinien mithilfe der Skype for Business Server-Systemsteuerung

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **PIN-Richtlinie**.
    
4. Klicken Sie auf der Seite **PIN-Richtlinie** auf die PIN-Richtlinie, die Sie anzeigen möchten. Klicken Sie dann auf **Bearbeiten** und anschließend auf **Details einblenden**.
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a>Anzeigen von Informationen zu PIN-Richtlinien mithilfe der Skype for Business Server-Verwaltungsshell

Wenn Sie Informationen zu den PIN-Richtlinien anzeigen möchten, verwenden Sie das Cmdlet **Get-CsPinPolicy**. Der folgende Befehl gibt zum Beispiel Informationen über eine einzelne PIN-Richtlinie mit der Identität „site:Redmond“ zurück:
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

Weitere Informationen, einschließlich einer vollständigen Syntax Beschreibung und einer Liste von Parametern, finden Sie unter [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).
  
## <a name="modify-the-global-pin-policy"></a>Ändern Sie die globale PIN-Richtlinie

Sie können die globale PIN-Richtlinie über die Skype for Business Server-Systemsteuerung oder über die Skype for Business Server-Verwaltungsshell ändern.
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a>Ändern der globalen PIN-Richtlinie für Einwahlkonferenzen mithilfe der Skype for Business Server-Systemsteuerung

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **PIN-Richtlinie**.
    
4. Klicken Sie auf der Seite **PIN-Richtlinie** auf **Global**, klicken Sie auf **Bearbeiten** und klicken Sie dann auf **Details anzeigen**.
    
5. Geben Sie unter **PIN-Richtlinie bearbeiten** im Feld **PIN-Mindestlänge** die gewünschte Mindestlänge für die PIN ein oder wählen Sie sie aus. In der Standardeinstellung beträgt die Mindestlänge fünf Ziffern.
    
6. Aktivieren Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben**, um anzugeben, nach wie vielen erfolglosen Anmeldeversuchen ein Benutzer gesperrt wird. Wenn Sie diese Option nicht aktivieren, wird die maximale Anzahl von Anmeldeversuchen basierend auf der PIN-Länge automatisch festgelegt. In der Standardeinstellung wird die maximale Anzahl von Anmeldeversuchen automatisch festgelegt.
    
7. Wenn Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben** aktiviert haben, geben Sie in **Maximale Anzahl von Anmeldeversuchen** die maximale Anzahl von Anmeldeversuchen ein, die Sie zulassen möchten. Sie können auch einen Wert auswählen.
    
8. Aktivieren Sie das Kontrollkästchen **PIN-Ablauf aktivieren**, um eine PIN-Ablaufdauer festzulegen. Wenn Sie diese Option nicht aktivieren, laufen PINs nie ab. In der Standardeinstellung ist für PINs kein Ablauf festgelegt.
    
9. Wenn Sie das Kontrollkästchen **PIN-Ablauf aktivieren** aktiviert haben, geben Sie unter **PIN-Ablauf nach (Tagen)** die Anzahl von Tagen ein, nach der PINs ablaufen.
    
10. Geben Sie unter **PIN-Verlaufszähler** die Anzahl von PINs ein, die ein Benutzer erstellen muss, bevor eine PIN erneut verwendet werden kann. In der Standardeinstellung können Benutzer ihre PINs erneut verwenden.
    
11. Aktivieren Sie das Kontrollkästchen **Allgemeine Muster zulassen**, um allgemeine Muster in PINs zuzulassen, beispielsweise aufeinanderfolgende und wiederholte Zahlen. Wenn Sie diese Option nicht aktivieren, sind nur komplexe Ziffernmuster zulässig. In der Standardeinstellung dürfen nur komplexe Ziffernmuster verwendet werden.
    
    > [!IMPORTANT]
    > Aus Sicherheitsgründen empfiehlt Microsoft, die Verwendung gängiger Muster nicht zuzulassen. 
  
12. Klicken Sie auf **Commit ausführen**.
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a>Ändern der globalen PIN-Richtlinie für Einwahlkonferenzen mithilfe der Skype for Business Server-Verwaltungsshell

Um die globale Richtlinie für Einwahlkonferenz-PINs zu ändern, verwenden Sie das Cmdlet **Set-CsPinPolicy**.
  
Der folgende Befehl ändert den Wert von „MinPasswordLength“ für alle PIN-Richtlinien, die für die Organisation konfiguriert wurden. Dazu ruft der Befehl zunächst das Cmdlet **Get-CsPinPolicy** ohne Parameter auf, um eine Auflistung aller vorhandenen PIN-Richtlinien abzurufen. Diese Auflistung wird dann an das Cmdlet **Set-CsPinPolicy** weitergeleitet, das wiederum den Wert der Eigenschaft „MinPasswordLength“ für jede Richtlinie in der Auflistung ändert.
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

Weitere Informationen, einschließlich einer vollständigen Syntax Beschreibung und einer Liste von Parametern, finden Sie unter [CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).
  
## <a name="create-a-user-or-site-pin-policy"></a>Erstellen Sie eine PIN-Richtlinie auf Benutzer- oder Standortebene

Sie können eine Benutzer-oder Website-PIN-Richtlinie mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell erstellen.
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Erstellen einer Benutzer-oder Website-PIN-Richtlinie mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **PIN-Richtlinie**.
    
4. Klicken Sie auf der Seite **PIN-Richtlinie** auf **Neu** und führen Sie eine der folgenden Aktionen aus:
    
   - Klicken Sie auf **Hinzufügen**, um eine Richtlinie auf Benutzerebene zu erstellen. Geben Sie im Abschnitt **Neue PIN-Richtlinie** in **Name** einen beschreibenden Namen für die Richtlinie ein.
    
   - Klicken Sie auf **Standortrichtlinie**, um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Suchfeld **Standort auswählen** einen Teil oder den gesamten Namen des Standorts ein, für den Sie eine Richtlinie erstellen möchten. Klicken Sie in der Liste der Standorte auf den gewünschten Standort und klicken Sie auf **OK**.
    
5. Geben Sie im Feld **Beschreibung** eine Beschreibung für die PIN-Richtlinie ein.
    
6. Geben Sie im Feld **PIN-Mindestlänge** die gewünschte Mindestlänge für die PIN ein oder wählen Sie sie aus. In der Standardeinstellung beträgt die Mindestlänge fünf Ziffern.
    
7. Aktivieren Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben**, um anzugeben, nach wie vielen erfolglosen Anmeldeversuchen ein Benutzer gesperrt wird. Wenn Sie diese Option nicht aktivieren, wird die maximale Anzahl von Anmeldeversuchen basierend auf der PIN-Länge automatisch festgelegt. In der Standardeinstellung wird die maximale Anzahl von Anmeldeversuchen automatisch festgelegt.
    
8. Wenn Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben** aktiviert haben, geben Sie in **Maximale Anzahl von Anmeldeversuchen** die maximale Anzahl von Anmeldeversuchen ein, die Sie zulassen möchten. Sie können auch einen Wert auswählen.
    
9. Aktivieren Sie das Kontrollkästchen **PIN-Ablauf aktivieren**, um eine PIN-Ablaufdauer festzulegen. Wenn Sie diese Option nicht aktivieren, laufen PINs nie ab. In der Standardeinstellung ist für PINs kein Ablauf festgelegt.
    
10. Wenn Sie das Kontrollkästchen **PIN-Ablauf aktivieren** aktiviert haben, geben Sie unter **PIN-Ablauf nach (Tagen)** die Anzahl von Tagen ein, nach der PINs ablaufen.
    
11. Geben Sie unter **PIN-Verlaufszähler** die Anzahl von PINs ein, die ein Benutzer erstellen muss, bevor eine PIN erneut verwendet werden kann. In der Standardeinstellung können Benutzer ihre PINs erneut verwenden.
    
12. Aktivieren Sie das Kontrollkästchen **Allgemeine Muster zulassen**, um allgemeine Muster in PINs zuzulassen, beispielsweise aufeinanderfolgende und wiederholte Zahlen. Wenn Sie diese Option nicht aktivieren, sind nur komplexe Ziffernmuster zulässig. In der Standardeinstellung dürfen nur komplexe Ziffernmuster verwendet werden.
    
    > [!IMPORTANT]
    > Aus Sicherheitsgründen empfiehlt Microsoft, die Verwendung gängiger Muster nicht zuzulassen. 
  
13. Klicken Sie auf **Commit ausführen**.
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Erstellen einer Benutzer-oder Website-PIN-Richtlinie mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie das Cmdlet **New-CsPinPolicy**, um eine PIN-Richtlinie auf Benutzer- oder Standortebene zu erstellen.
  
Der folgende Befehl erstellt eine neue PIN-Richtlinie mit dem Identitätswert „site:Redmond“. Dieser Befehl enthält nur einen optionalen Parameter, „MinPasswordLength“, mit dem die Eigenschaft „MinPasswordLength“ auf 7 festgelegt wird. Alle übrigen Richtlinieneigenschaften werden mit den Standardwerten konfiguriert.
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 Weitere Informationen, einschließlich einer vollständigen Syntax Beschreibung und einer Liste von Parametern, finden Sie unter [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).
  
## <a name="modify-a-user-or-site-pin-policy"></a>Passen Sie eine PIN-Richtlinie auf Benutzer- oder Standortebene an

Sie können eine Benutzer-oder Website-PIN-Richtlinie mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell ändern.
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Ändern einer Benutzer-oder Website-PIN-Richtlinie mithilfe der Skype for Business Server-Systemsteuerung

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **PIN-Richtlinie**.
    
4. Klicken Sie auf der Seite **PIN-Richtlinie** auf die PIN-Richtlinie, die Sie ändern möchten. Klicken Sie dann auf **Bearbeiten** und anschließend auf **Details einblenden**.
    
5. Ändern Sie im Abschnitt **PIN-Richtlinie bearbeiten** eine beliebige der Richtlinieneinstellungen. Hiervon ausgenommen ist der Richtlinienname, dieser kann nicht geändert werden.
    
6. Klicken Sie auf **Commit ausführen**.
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Ändern einer Benutzer-oder Website-PIN-Richtlinie mithilfe der Skype for Business Server-Verwaltungsshell

Wenn die Richtlinie für Einwahlkonferenz-PINs geändert werden soll, verwenden Sie das Cmdlet **Set-CsPinPolicy**.
  
Der folgende Befehl ändert die dem Standort „Redmond“ zugewiesene PIN-Richtlinie. In diesem Fall ändert der Befehl den Wert der Eigenschaft „MinPasswordLength“ in 10. Das heißt, dass neue PINs mindestens 10 Stellen umfassen müssen:
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

Weitere Informationen, einschließlich einer vollständigen Syntax Beschreibung und einer Liste von Parametern, finden Sie unter [CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).
  
## <a name="delete-a-user-or-site-pin-policy"></a>Löschen Sie eine PIN-Richtlinie auf Benutzer- oder Standortebene

Sie können eine Benutzer-oder Website-PIN-Richtlinie mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell löschen.
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Löschen einer Benutzer-oder Website-PIN-Richtlinie mithilfe der Skype for Business Server-Systemsteuerung

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **PIN-Richtlinie**.
    
4. Klicken Sie auf der Seite **PIN-Richtlinie** auf die PIN-Richtlinie, die Sie ändern möchten. Klicken Sie dann auf **Bearbeiten** und anschließend auf **löschen**.
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Löschen einer Benutzer-oder Website-PIN-Richtlinie mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie das Cmdlet **Remove-CsPinPolicy**, um eine PIN-Richtlinie auf Benutzer- oder Standortebene zu löschen.
  
Der folgende Befehl entfernt alle PIN-Richtlinien, die auf Standortebene konfiguriert wurden. Hierzu wird das Cmdlet **Get-CsPinPolicy** mit dem Parameter „Filter“ aufgerufen, um eine Auflistung aller Richtlinien zurückzugeben, deren Identitätswert mit der Zeichenfolge „site:“ beginnt. Diese Auflistung wird dann an das Cmdlet **Remove-CsPinPolicy** weitergeleitet, das jede Richtlinie in der Auflistung löscht.
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

Weitere Informationen einschließlich einer vollständigen Syntax Beschreibung und einer Liste der Parameter finden Sie unter [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).
  


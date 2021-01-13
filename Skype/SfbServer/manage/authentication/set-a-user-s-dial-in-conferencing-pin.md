---
title: Festlegen der Einwahlkonferenz-PIN eines Benutzers in Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 'Zusammenfassung: Festlegen der Einwahlkonferenz-PIN eines Benutzers für Skype for Business Server.'
ms.openlocfilehash: cd7375519fa9fc161c6414dcf1b9d0fbf6de6ef0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828297"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a>Festlegen der Einwahlkonferenz-PIN eines Benutzers in Skype for Business Server
 
**Zusammenfassung:** Festlegen der Einwahlkonferenz-PIN eines Benutzers für Skype for Business Server.
  
Um als authentifizierter Benutzer an einer Einwahlkonferenz teilnehmen zu können, benötigt ein Skype for Business Server-Benutzer mit Active Directory Domain Services (AD DS)-Anmeldeinformationen eine persönliche Identifikationsnummer (PIN). Wenn ein Benutzer die Einwahlkonferenz-PIN vergisst oder die PIN nicht mithilfe von Skype for Business Server festgelegt hat, können Sie die PIN des Benutzers über die Skype for Business Server-Systemsteuerung festlegen. Die PIN kann entweder automatisch generiert oder manuell erstellt werden.
  
> [!NOTE]
> Bestimmte Eigenschaften der PIN, beispielsweise die Mindestlänge, können als Richtlinie konfiguriert werden. Zusätzlich zur globalen Richtlinie können Sie eine PIN-Richtlinie für einzelne Standorte oder Benutzer konfigurieren. 
  
### <a name="to-set-a-users-pin"></a>So legen Sie die PIN eines Benutzers

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:
    
   - Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, und klicken Sie dann auf **Suchen**.
    
   - Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.
    
5. (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse zu beschränken:
    
   a. Klicken Sie auf **Filter hinzufügen**.
    
   b. Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.
    
   c. Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).
    
   d. Geben Sie je nach ausgewählter Benutzereigenschaft entweder das Kriterium für die Filterung der Suchergebnisse ein, oder klicken Sie auf den Pfeil in der Dropdownliste.
    
    > [!TIP]
    > Klicken Sie auf **Filter hinzufügen**, um zusätzliche Suchklauseln einzugeben. 
  
   e. Klicken Sie auf **Suchen**.
    
    > [!NOTE]
    > Ist die PIN gesperrt, müssen Sie die Sperre zunächst aufheben, bevor Sie die PIN festlegen können. Klicken Sie zum Aufheben der Sperre auf den Benutzer, dann auf **Aktion** und schließlich auf **PIN-Nummer entsperren**. 
  
6. Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **PIN festlegen**.
    
7. Führen Sie im Dialogfeld **PIN festlegen** einen der folgenden Schritte aus:
    
   - Damit Skype for Business Server die PIN des Benutzers generieren kann, wählen Sie "Automatisches Generieren einer gültigen **PIN"** (Standardeinstellung) aus.
    
   - Zum Erstellen einer eigenen PIN klicken Sie auf **Bestimmte PIN manuell eingeben**, klicken Sie auf das Textfeld, und geben Sie anschließend eine PIN ein, welche die in Ihren PIN-Richtlinieneinstellungen angegebenen PIN-Anforderungen erfüllt.
    
8. Klicken Sie auf **OK**.
    
9. Führen Sie im Abschnitt **PIN festlegen** eine der folgenden Aktionen aus: 
    
   - Aktivieren Sie das Kontrollkästchen **PIN anzeigen**, um die PIN anzuzeigen, kopieren Sie die PIN, und teilen Sie sie dem Benutzer über die bevorzugte Methode Ihrer Organisation mit.
    
   - Klicken Sie auf **E-Mail-Anwendung zum Senden der neuen PIN an den Benutzer öffnen**, um die PIN per E-Mail zu senden. Wenn Sie Microsoft Office Outlook als E-Mail-Client verwenden, wird die PIN automatisch in die neue E-Mail-Nachricht kopiert. Wenn Sie einen anderen E-Mail-Client einsetzen, aktivieren Sie das Kontrollkästchen **PIN anzeigen**, und kopieren Sie die PIN anschließend in die E-Mail-Nachricht.
    
10. Klicken Sie auf **Schließen**.
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Zuweisen einer Benutzer-PIN mithilfe Windows PowerShell Cmdlets

Sie können mithilfe des Cmdlets auch PIN-Nummern Set-CsClientPin zuweisen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Schnellstart: Verwalten von Microsoft Lync Server 2010 mithilfe von Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Prozess ist in Skype for Business Server identisch. 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a>So weisen Sie einem Benutzer automatisch eine PIN zu

Der folgende Befehl weist dem Benutzer Ken Myer eine PIN zu. Da der Parameter "Pin" nicht enthalten ist, generiert Skype for Business Server automatisch die PIN-Nummer und weist sie zu.
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a>So weisen Sie einem Benutzer eine bestimmte PIN zu

Der folgende Befehl verwendet den PIN-Parameter, um dem Benutzer Ken Myer die PIN 121989 zuzuweisen.
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Set-CsClientPin".](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps)
  


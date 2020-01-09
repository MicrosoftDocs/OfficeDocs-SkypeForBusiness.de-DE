---
title: Einrichten der PIN für Einwahlkonferenzen von Benutzern in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 'Zusammenfassung: Einrichten der PIN für Einwahlkonferenzen eines Benutzers für Skype for Business Server.'
ms.openlocfilehash: 83d1aae54d6e8be4f31b5bd27b6a568d6d88db1e
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992282"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a>Einrichten der PIN für Einwahlkonferenzen von Benutzern in Skype for Business Server
 
**Zusammenfassung:** Die PIN für Einwahlkonferenzen eines Benutzers für Skype for Business Server festzulegen.
  
Um an einer Einwahlkonferenz als authentifizierter Benutzer teilzunehmen, erfordert ein Skype for Business Server-Benutzer mit den Anmeldeinformationen für Active Directory-Domänendienste (AD DS) eine persönliche Identifikationsnummer (PIN). Wenn ein Benutzer die PIN für Einwahlkonferenzen vergisst oder die PIN nicht über Skype for Business Server festgesetzt hat, können Sie die PIN des Benutzers über die Skype for Business Server-Systemsteuerung festlegen. Die PIN kann entweder automatisch generiert oder manuell erstellt werden.
  
> [!NOTE]
> Bestimmte Eigenschaften der PIN, beispielsweise die Mindestlänge, können als Richtlinie konfiguriert werden. Zusätzlich zur globalen Richtlinie können Sie eine PIN-Richtlinie für einzelne Standorte oder Benutzer konfigurieren. 
  
### <a name="to-set-a-users-pin"></a>So richten Sie die PIN eines Benutzers ein

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:
    
   - Geben Sie im Feld **Benutzer suchen** den vollständigen oder teilweisen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein und klicken Sie dann auf **Suchen**.
    
   - Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.
    
5. (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:
    
   a. Klicken Sie auf **Filter hinzufügen**.
    
   b. Geben Sie die Benutzereigenschaft ein, indem Sie sie über die Tastatur eintippen oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.
    
   c. Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).
    
   d. Je nachdem, welche Benutzereigenschaft Sie ausgewählt haben, geben Sie nun die Kriterien ein, mit denen Sie die Suchergebnisse filtern möchten, oder treffen eine entsprechende Auswahl in der Dropdownliste.
    
    > [!TIP]
    > Klicken Sie auf **Filter hinzufügen**, um zusätzliche Suchklauseln einzugeben. 
  
   e. Klicken Sie auf **Suchen**.
    
    > [!NOTE]
    > Ist die PIN gesperrt, müssen Sie die Sperre zunächst aufheben, bevor Sie die PIN festlegen können. Klicken Sie zum Aufheben der Sperre auf den Benutzer, dann auf **Aktion** und auf **PIN entsperren**. 
  
6. Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **PIN festlegen**.
    
7. Führen Sie im Dialogfeld **PIN festlegen** einen der folgenden Schritte aus:
    
   - Wenn Sie zulassen möchten, dass Skype for Business Server die PIN des Benutzers generiert, wählen Sie **automatisch eine gültige Pin generieren** (Standardeinstellung) aus.
    
   - Zum Erstellen einer eigenen PIN klicken Sie auf **Bestimmte PIN von Hand eingeben**, klicken Sie auf das Textfeld und geben Sie anschließend eine PIN ein, welche die in Ihren PIN-Richtlinieneinstellungen angegebenen PIN-Anforderungen erfüllt.
    
8. Klicken Sie anschließend auf **OK**.
    
9. Führen Sie im Abschnitt **PIN festlegen** eine der folgenden Aktionen aus: 
    
   - Aktivieren Sie das Kontrollkästchen **PIN anzeigen**, um die PIN anzuzeigen, kopieren Sie die PIN und teilen Sie sie dem Benutzer über die bevorzugte Methode Ihrer Organisation mit.
    
   - Klicken Sie auf **E-Mail-Client öffnen, um die neue PIN an den Benutzer zu senden**, um die PIN per E-Mail zu senden. Wenn Sie Microsoft Office Outlook als E-Mail-Client verwenden, wird die PIN automatisch in die neue E-Mail-Nachricht kopiert. Wenn Sie einen anderen E-Mail-Client einsetzen, aktivieren Sie das Kontrollkästchen **PIN anzeigen** und kopieren Sie die PIN anschließend in die E-Mail-Nachricht.
    
10. Klicken Sie auf **Schließen**.
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Zuweisen einer Benutzer-PIN mithilfe von Windows PowerShell-Cmdlets

Sie können Benutzern mithilfe des Cmdlets „Lock-Set-CsClientPin“ PINs zuweisen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch. 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a>So weisen Sie Benutzern automatisch PINs zu

Der folgende Befehl weist dem Benutzer Ken Myer eine PIN zu. Da der PIN-Parameter nicht enthalten ist, wird von Skype for Business Server automatisch die PIN-Nummer generiert und zugewiesen.
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a>So weisen Sie einem Benutzer eine bestimmte PIN zu

Der folgende Befehl verwendet den Parameter „Pin“, um dem Benutzer Ken Myer die PIN 121989 zuzuweisen.
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) ".
  


---
title: Anzeigen von Benutzer-PIN-Informationen in Skype for Business Server
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
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Zusammenfassung: Anzeigen von Benutzer-PIN-Informationen in Skype for Business Server.'
ms.openlocfilehash: 1b280f4e00bacab5c7def0d6ff6c274f64d9ef8651b6d2b0d328867260e77449
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315641"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a>Anzeigen von Benutzer-PIN-Informationen in Skype for Business Server
 
**Zusammenfassung:** Anzeigen von Benutzer-PIN-Informationen in Skype for Business Server.
  
Um einer Einwahlkonferenz als authentifizierter Benutzer beizutreten, benötigt ein Skype for Business Server Benutzer mit Active Directory Domain Services (AD DS)-Anmeldeinformationen eine persönliche Identifikationsnummer (PIN). Sie können die PIN-Informationen eines Benutzers in Skype for Business Server Systemsteuerung anzeigen.
  
> [!NOTE]
> Sie können PIN-Statusinformationen anzeigen, z. B. ob die PIN festgelegt wurde oder wann die PIN zuletzt geändert wurde, aber Sie können die aktuelle PIN nicht anzeigen, indem Sie sich den PIN-Status ansehen. Wenn ein Benutzer seine PIN verloren hat, können Sie sie zurücksetzen, indem Sie die Verfahren unter [Festlegen der Einwahlkonferenz-PIN eines Benutzers in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>So zeigen Sie die PIN eines Benutzers in Skype for Business Server Systemsteuerung an

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.  
    
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
    > Ist die PIN gesperrt, müssen Sie die Sperre zunächst aufheben, bevor Sie die PIN festlegen können. Klicken Sie zum Aufheben der Sperre auf den Benutzer, dann auf **Aktion** und auf **PIN entsperren**. 
  
6. Klicken Sie auf einen Benutzer in den Suchergebnissen und dann auf **Aktion** und auf **PIN-Status anzeigen**.
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Benutzer-PIN-Informationen mithilfe Windows PowerShell Cmdlets

Sie können die PIN-Informationen für Benutzer mit dem Get-CsClientPinInfo-Cmdlet anzeigen. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Schnellstart: Verwalten von Microsoft Lync Server 2010 mithilfe von Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-view-user-pin-information"></a>So zeigen Sie die PIN-Informationen von Benutzern an

Um PIN-Informationen für einen Benutzer anzuzeigen, geben Sie einen Befehl ähnlich dem folgenden in der Skype for Business Server Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Get-CsConferenceDisclaimer".](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps)
  
## <a name="see-also"></a>Siehe auch

[Festlegen der Einwahlkonferenz-PIN eines Benutzers in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)
  
[Sperren oder Entsperren einer Benutzer-PIN in Skype for Business Server](lock-or-unlock-a-user-pin.md)
---
title: Verwalten von Benutzerkonten für Skype for Business Server
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
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: In den Abschnitten in diesem Artikel wird beschrieben, wie Active Directory-Benutzer von Skype for Business Server aktiviert, vorübergehend deaktiviert oder entfernt werden.
ms.openlocfilehash: 0cf78b4ebe7023bc5a0f1b4af75c5d9e5a45db1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103121"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Verwalten von Benutzerkonten für Skype for Business Server

In den Abschnitten in diesem Artikel wird beschrieben, wie Active Directory-Benutzer von Skype for Business Server aktiviert, vorübergehend deaktiviert oder entfernt werden.

Informationen zum Aktivieren eines Active Directory-Benutzers finden Sie unter [Create a New User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)). Informationen zum Löschen eines Active Directory-Benutzers finden Sie [unter Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).

Diese Verfahren sollten während eines Wartungsfensters ausgeführt werden, wenn die Skype for Business-Nutzung am niedrigsten ist. Ob dies täglich oder wöchentlich erfolgt, hängt von den Anforderungen Ihrer Organisation ab.

Dieser Artikel enthält die folgenden Verfahren:

- [So suchen Sie nach einem oder mehreren Benutzern](user-accounts.md#Search)

- [Hinzufügen und Aktivieren eines neuen Skype for Business Server-Benutzers](user-accounts.md#Add)

- [Deaktivieren oder erneutes Aktivieren eines zuvor für Skype for Business Server aktivierten Benutzerkontos](user-accounts.md#Disable)

- [Deaktivieren eines Benutzers für Enterprise-VoIP](user-accounts.md#Disable_EV)

- [Entfernen eines Benutzerkontos mit der Skype for Business Server-Verwaltungsshell](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>So suchen Sie nach einem oder mehreren Benutzern
<a name="Search"> </a>

Sie können die Ergebnisse einer Suchabfrage verwenden, um Active Directory-Benutzer für Skype for Business Server zu konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URIs (Uniform Resource Identifier) nach Benutzern suchen.

Sie können mithilfe der Skype for Business Server-Systemsteuerung oder des Active Directory Users and Computers-Snap-Ins nach Benutzern suchen. Im folgenden Verfahren wird beschrieben, wie Sie die Skype for Business Server-Systemsteuerung verwenden, um nach Benutzern zu suchen.

> [!NOTE]
> In einer Umgebung mit einer zentralen Gesamtstrukturtopologie sind die Suchergebnisse möglicherweise nicht genau, wenn Sie über die E-Mail-Adresse des Benutzers nach einem Benutzer suchen. Stattdessen können Sie Benutzer durch Angabe eines SIP-Adressenpräfixes suchen, z. B. "sip:name", einen Suchfilter hinzufügen und eine SIP-Adresse auswählen, die einen Teil einer E-Mail-Adresse enthält, oder das Cmdlet **Get-CSUser** verwenden.

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen, die SIP-Adresse oder den Anschluss-URI des zu suchenden Benutzerkontos ein, und klicken Sie dann auf **Suchen**.

5. (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse zu beschränken:

   a. Klicken Sie in der oberen rechten Ecke des Bildschirms oberhalb von **Suchergebnisse** auf die Pfeiltaste zum Erweitern des Fensters, und klicken Sie dann auf **Filter hinzufügen**.

   b. Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder auf den Pfeil in der Dropdownliste klicken, um eine Benutzereigenschaft auszuwählen.

   c. Klicken Sie in der Dropdownliste **Gleich** auf **Gleich** oder **Ungleich**.

   d. Geben Sie im Textfeld die Suchkriterien ein, die Sie zum Filtern der Suchergebnisse verwenden möchten, und klicken Sie dann auf **Suchen**.

6. Die Suchergebnisse werden unter **Suchergebnisse** angezeigt. Sie können bestimmte oder alle Benutzer in der Liste auswählen und für die ausgewählten Benutzer Konfigurationsaufgaben durchführen.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Hinzufügen und Aktivieren eines neuen Skype for Business Server-Benutzers
<a name="Add"> </a>

Nachdem Sie ein Benutzerkonto in Active Directory-Benutzern und -Computern aktiviert haben, können Sie die Skype for Business Server-Systemsteuerung verwenden, um neue Skype for Business Server-Benutzerkonten zu erstellen und zu aktivieren, indem Sie skype for Business Server einen Active Directory-Benutzer hinzufügen.

Sie können auch ein Cmdlet verwenden, insbesondere [Enable-CsUser](/powershell/module/skype/enable-csuser?view=skype-ps).

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Klicken Sie **auf Benutzer aktivieren.**

5. Klicken Sie **im Dialogfeld Neuer Lync Server-Benutzer** auf **Hinzufügen**.

6. Geben  Sie im Feld Benutzer suchen den namen, den Anzeigenamen, den Vornamen, den Nachnamen, den Sicherheitskonten-Manager-Kontonamen, die E-Mail-Adresse, den Benutzerprinzipalnamen (User Principal Name, UPN) oder die Telefonnummer des von Ihnen gesuchten Active Directory-Benutzerkontos ein, und klicken Sie dann auf **Suchen**.

7. Wählen Sie in der Tabelle das Konto aus, das Sie Skype for Business Server hinzufügen möchten, und klicken Sie dann auf **OK**.

8. Weisen Sie den Benutzer einem Pool zu, geben Sie weitere Details an, weisen Sie die Richtlinien dem Benutzer zu, den Sie möchten, und klicken Sie dann auf **Aktivieren**.

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Deaktivieren oder erneutes Aktivieren eines zuvor für Skype for Business Server aktivierten Benutzerkontos
<a name="Disable"> </a>

Sie können das folgende Verfahren verwenden, um ein zuvor aktiviertes Benutzerkonto in Skype for Business Server zu deaktivieren, ohne die Skype for Business Server-Einstellungen zu verlieren, die Sie für das Benutzerkonto konfiguriert haben. Da Sie die Einstellungen für das Skype for Business Server-Benutzerkonto nicht verlieren, können Sie ein zuvor aktiviertes Benutzerkonto erneut aktivieren, ohne das Benutzerkonto neu konfigurieren zu müssen.

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das deaktiviert oder erneut aktiviert werden soll, und klicken Sie dann auf **Suchen**.

5. Klicken Sie in der Tabelle auf das Benutzerkonto, das deaktiviert oder erneut aktiviert werden soll.

6. Führen Sie im Menü **Aktion** einen der folgenden Schritte aus:

   - Klicken Sie auf Vorübergehend deaktivieren für Lync **Server,** um das Benutzerkonto für Skype for Business Server vorübergehend zu deaktivieren.

   - Klicken Sie auf Erneut aktivieren für **Lync Server,** um das Benutzerkonto für Skype for Business Server zu aktivieren.

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Deaktivieren oder Erneutes Aktivieren von Benutzerkonten mithilfe von Windows Powershell

Benutzerkonten können mithilfe des **Cmdlets Set-CsUser** vorübergehend deaktiviert und später wieder aktiviert werden. Sie können dieses Cmdlet entweder über die Skype for Business Server Management Shell oder über eine Remotesitzung von Windows PowerShell. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.

### <a name="to-disable-a-user-account"></a>So deaktivieren Sie ein Benutzerkonto

- Zum vorübergehenden Deaktivieren eines Benutzerkontos setzen Sie den Wert der Eigenschaft "Enabled" auf "False" ($False). Beispiel:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>So aktivieren Sie ein Benutzerkonto erneut

- Zum erneuten Aktivieren eines deaktivierten Benutzerkontos setzen Sie den Wert der Eigenschaft "Enabled" auf "True" ($True). Beispiel:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Weitere Informationen finden Sie im Hilfethema für das [Cmdlet Set-CsUser.](/powershell/module/skype/set-csuser?view=skype-ps)

## <a name="disable-a-user-for-enterprise-voice"></a>Deaktivieren eines Benutzers für Enterprise-VoIP
<a name="Disable_EV"> </a>

Verwenden Sie das folgende Verfahren, um Enterprise-VoIP für ein Benutzerkonto zu deaktivieren, das für Skype for Business Server aktiviert ist.

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>So deaktivieren Sie ein Benutzerkonto für Enterprise-VoIP

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.

5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für die Enterprise-VoIP.

6. Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

7. Klicken Sie auf der Seite **Lync Server-Benutzer bearbeiten** unter **Telefonie** auf eine beliebige Option außer **Enterprise-VoIP**.

    > [!NOTE]
    > Klicken Sie unter Telefonie auf **Audio/Video deaktiviert,** um zu verhindern, dass ein Benutzer Audio- oder Videoanrufe mit Lync macht. 

8. Klicken Sie auf **Commit ausführen**.

Der Benutzer kann das Feature Enterprise-VoIP verwenden. Verwandte Informationen: <br/>[Enterprise-VoIP und Mobilität](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype for Business Server-Verwaltungsshell](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Entfernen eines Benutzerkontos mit der Skype for Business Server-Verwaltungsshell
<a name="Remove"> </a>

Sie können das folgende Verfahren verwenden, um ein zuvor hinzugefügtes Benutzerkonto in Skype for Business Server zu entfernen.

> [!NOTE]
> Wenn Sie einen Benutzer entfernen, gehen alle Einstellungen verloren, die Sie für das Benutzerkonto konfiguriert haben. Wenn Sie stattdessen ein Benutzerkonto vorübergehend deaktivieren möchten, lesen Sie Deaktivieren oder erneutes Aktivieren eines Benutzerkontos, das zuvor für [Skype for Business Server aktiviert wurde.](user-accounts.md#Disable)

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager, Sicherheitskonto-Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das deaktiviert oder erneut aktiviert werden soll, und klicken Sie dann auf **Suchen**.

5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie entfernen möchten.

6. Klicken Sie im Menü **Aktion** auf **Aus Lync Server entfernen**. Daraufhin wird ein Dialogfeld angezeigt.

7. Wählen Sie im Dialogfeld **OK** aus, um den Benutzer zu entfernen.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Entfernen von Benutzerkonten mit Windows Powershell-Cmdlets

Sie können Benutzerkonten mithilfe des cmdlets Disable-CsUser entfernen. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung ausgeführt Windows PowerShell. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.

### <a name="to-remove-a-user-account"></a>So entfernen Sie ein Benutzerkonto
Sie können das Cmdlet Disable-CsUser verwenden, um ein Benutzerkonto zu entfernen. Beispiel:

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

Weitere Informationen finden Sie im Hilfethema für das [Cmdlet Disable-CsUser.](/powershell/module/skype/disable-csuser?view=skype-ps)

## <a name="see-also"></a>Siehe auch
<a name="Remove"> </a>

[Enable-CsUser](/powershell/module/skype/enable-csuser?view=skype-ps)

[Disable-CsUser](/powershell/module/skype/disable-csuser?view=skype-ps)
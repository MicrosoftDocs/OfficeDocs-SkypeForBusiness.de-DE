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
description: In den Abschnitten in diesem Artikel wird beschrieben, wie Active Directory-Benutzer in Skype for Business Server aktiviert, vorübergehend deaktiviert oder entfernt werden.
ms.openlocfilehash: aa1b1b21ba089815af20b61da3360179fb10935e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832775"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Verwalten von Benutzerkonten für Skype for Business Server

In den Abschnitten in diesem Artikel wird beschrieben, wie Active Directory-Benutzer in Skype for Business Server aktiviert, vorübergehend deaktiviert oder entfernt werden.

Informationen zum Aktivieren eines Active Directory-Benutzers finden Sie unter ["Erstellen eines neuen Benutzerkontos".](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx) Informationen zum Löschen eines Active Directory-Benutzers finden Sie unter ["Löschen eines Benutzerkontos".](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx)

Diese Verfahren sollten während eines Wartungsfensters ausgeführt werden, wenn die Skype for Business-Nutzung am geringsten ist. Ob dies nach einem täglichen oder wöchentlichen Zeitplan erfolgt, hängt von den Anforderungen Ihrer Organisation ab.

Dieser Artikel enthält die folgenden Verfahren:

- [So suchen Sie nach einem oder mehreren Benutzern](user-accounts.md#Search)

- [Hinzufügen und Aktivieren eines neuen Skype for Business Server-Benutzers](user-accounts.md#Add)

- [Deaktivieren oder erneutes Aktivieren eines Benutzerkontos, das zuvor für Skype for Business Server aktiviert war](user-accounts.md#Disable)

- [Deaktivieren eines Benutzers für Enterprise-VoIP](user-accounts.md#Disable_EV)

- [Entfernen eines Benutzerkontos mit der Skype for Business Server-Verwaltungsshell](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>So suchen Sie nach einem oder mehreren Benutzern
<a name="Search"> </a>

Sie können die Ergebnisse einer Suchabfrage verwenden, um Active Directory-Benutzer für Skype for Business Server zu konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URIs (Uniform Resource Identifier) nach Benutzern suchen.

Sie können mithilfe der Skype for Business Server-Systemsteuerung oder des Active Directory-Snap-Ins "Benutzer und Computer" nach Benutzern suchen. Im folgenden Verfahren wird beschrieben, wie Sie die Skype for Business Server-Systemsteuerung verwenden, um nach Benutzern zu suchen.

> [!NOTE]
> In einer Umgebung mit einer Topologie mit zentraler Gesamtstruktur sind die Suchergebnisse möglicherweise nicht genau, wenn Sie nach einem Benutzer über die E-Mail-Adresse des Benutzers suchen. Stattdessen können Sie Benutzer durch Angabe eines SIP-Adressenpräfixes suchen, z. B. "sip:name", einen Suchfilter hinzufügen und eine SIP-Adresse auswählen, die einen Teil einer E-Mail-Adresse enthält, oder das Cmdlet **Get-CSUser** verwenden.

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

Nachdem Sie ein Benutzerkonto in Active Directory-Benutzer und -Computer aktiviert haben, können Sie die Skype for Business Server-Systemsteuerung verwenden, um neue Skype for Business Server-Benutzerkonten zu erstellen und zu aktivieren, indem Sie skype for Business Server einen Active Directory-Benutzer hinzufügen.

Sie können auch ein Cmdlet verwenden, insbesondere [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Klicken **Sie auf "Benutzer aktivieren".**

5. Klicken Sie **im Dialogfeld "Neuer Lync Server-Benutzer"** auf **"Hinzufügen".**

6. Geben  Sie im Feld "Benutzer suchen" den namen, anzeigenamen, vornamen, nachnamen, den Kontonamen des Security Accounts Managers (SAM), die E-Mail-Adresse, den Benutzerprinzipalnamen (UpN) oder die Telefonnummer des active Directory-Benutzerkontos ein, das Sie suchen möchten, und klicken Sie dann auf **"Suchen".**

7. Wählen Sie in der Tabelle das Konto aus, das Sie Skype for Business Server hinzufügen möchten, und klicken Sie dann auf **"OK".**

8. Weisen Sie den Benutzer einem Pool zu, geben Sie weitere Details an, weisen Sie dem Benutzer die Richtlinien zu, und klicken Sie dann auf **"Aktivieren".**

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Deaktivieren oder erneutes Aktivieren eines Benutzerkontos, das zuvor für Skype for Business Server aktiviert war
<a name="Disable"> </a>

Mit dem folgenden Verfahren können Sie ein zuvor aktiviertes Benutzerkonto in Skype for Business Server deaktivieren, ohne die Skype for Business Server-Einstellungen zu verlieren, die Sie für das Benutzerkonto konfiguriert haben. Da die Einstellungen für das Skype for Business Server-Benutzerkonto nicht verloren gehen, können Sie ein zuvor aktiviertes Benutzerkonto erneut aktivieren, ohne das Benutzerkonto neu konfigurieren zu müssen.

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das deaktiviert oder erneut aktiviert werden soll, und klicken Sie dann auf **Suchen**.

5. Klicken Sie in der Tabelle auf das Benutzerkonto, das deaktiviert oder erneut aktiviert werden soll.

6. Führen Sie im Menü **Aktion** einen der folgenden Schritte aus:

   - Klicken Sie auf "Vorübergehend für Lync Server deaktivieren", um das Benutzerkonto für Skype for Business **Server vorübergehend zu deaktivieren.**

   - Klicken Sie auf **"Erneut aktivieren"** für Lync Server, um das Benutzerkonto für Skype for Business Server zu aktivieren.

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Verwenden von Windows Powershell zum Deaktivieren oder erneuten Aktivieren von Benutzerkonten

Benutzerkonten können mit dem Cmdlet **"Set-CsUser"** vorübergehend deaktiviert und später wieder aktiviert werden. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell. Details zur Verwendung von Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Schnellstart: Verwalten von Microsoft Lync Server 2010 mithilfe von Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Prozess ist in Skype for Business Server identisch.

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

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Set-CsUser".](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)

## <a name="disable-a-user-for-enterprise-voice"></a>Deaktivieren eines Benutzers für Enterprise-VoIP
<a name="Disable_EV"> </a>

Verwenden Sie das folgende Verfahren, Enterprise-VoIP für ein Benutzerkonto zu deaktivieren, das für Skype for Business Server aktiviert ist.

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>So deaktivieren Sie ein Benutzerkonto für Enterprise-VoIP

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.

5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für die Enterprise-VoIP.

6. Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

7. Klicken Sie auf der Seite **Lync Server-Benutzer bearbeiten** unter **Telefonie** auf eine beliebige Option außer **Enterprise-VoIP**.

    > [!NOTE]
    > Klicken Sie unter "Telefonie" auf "Audio/Video deaktiviert", um zu verhindern, dass ein Benutzer Audio- oder **Videoanrufe** über Lync macht. 

8. Klicken Sie auf **Commit ausführen**.

Der Benutzer kann das Feature jetzt nicht Enterprise-VoIP verwenden. Verwandte Informationen: <br/>[Enterprise-VoIP und Mobilität](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype for Business Server-Verwaltungsshell](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Entfernen eines Benutzerkontos mit der Skype for Business Server-Verwaltungsshell
<a name="Remove"> </a>

Mit dem folgenden Verfahren können Sie ein zuvor hinzugefügtes Benutzerkonto in Skype for Business Server entfernen.

> [!NOTE]
> Wenn Sie einen Benutzer entfernen, gehen alle Einstellungen verloren, die Sie für das Benutzerkonto konfiguriert haben. Wenn Sie stattdessen ein Benutzerkonto vorübergehend deaktivieren möchten, lesen Sie die Informationen unter Deaktivieren oder erneutes Aktivieren eines Benutzerkontos, das zuvor für [Skype for Business Server aktiviert wurde.](user-accounts.md#Disable)

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager, Sicherheitskonto-Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das deaktiviert oder erneut aktiviert werden soll, und klicken Sie dann auf **Suchen**.

5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie entfernen möchten.

6. Klicken Sie im Menü **Aktion** auf **Aus Lync Server entfernen**. Daraufhin wird ein Dialogfeld angezeigt.

7. Wählen Sie im Dialogfeld **OK** aus, um den Benutzer zu entfernen.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Entfernen von Benutzerkonten mit Windows -Powershell-Cmdlets

Sie können Benutzerkonten mit dem cmdlet Disable-CsUser entfernen. Dieses Cmdlet kann entweder in der Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung ausgeführt Windows PowerShell. Details zur Verwendung von Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Schnellstart: Verwalten von Microsoft Lync Server 2010 mithilfe von Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Prozess ist in Skype for Business Server identisch.

### <a name="to-remove-a-user-account"></a>So entfernen Sie ein Benutzerkonto
Sie können das Cmdlet Disable-CsUser verwenden, um ein Benutzerkonto zu entfernen. Beispiel:

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Disable-CsUser".](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)

## <a name="see-also"></a>Siehe auch
<a name="Remove"> </a>

[Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)

---
title: Verwalten von Benutzerkonten für Skype for Business Server
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
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: In den Abschnitten in diesem Artikel wird beschrieben, wie Sie Active Directory Benutzer aus Skype for Business Server aktivieren, vorübergehend deaktivieren oder entfernen.
ms.openlocfilehash: aa1ed16c39141cbcd6542f2c7e254a278c345826
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009638"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Verwalten von Benutzerkonten für Skype for Business Server

In den Abschnitten in diesem Artikel wird beschrieben, wie Sie Active Directory Benutzer aus Skype for Business Server aktivieren, vorübergehend deaktivieren oder entfernen.

Informationen zum Aktivieren eines Active Directory Benutzers finden Sie unter [Erstellen eines neuen Benutzerkontos](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx). Informationen zum Löschen eines Active Directory Benutzers finden Sie unter [Löschen eines Benutzerkontos](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx).

Diese Verfahren sollten während eines Wartungsfensters ausgeführt werden, wenn Skype for Business Verwendung am niedrigsten ist. Ob dies für einen täglichen oder wöchentlichen Zeitplan erfolgt, hängt von den Anforderungen Ihrer Organisation ab.

Dieser Artikel enthält die folgenden Verfahren:

- [So suchen Sie nach einem oder mehreren Benutzern](user-accounts.md#Search)

- [Hinzufügen und Aktivieren eines neuen Skype for Business Server Benutzers](user-accounts.md#Add)

- [Deaktivieren oder erneutes Aktivieren eines zuvor für Skype for Business Server aktivierten Benutzerkontos](user-accounts.md#Disable)

- [Deaktivieren eines Benutzers für Enterprise-VoIP](user-accounts.md#Disable_EV)

- [Entfernen eines Benutzerkontos mit der Skype for Business Server Management-Shell](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>So suchen Sie nach einem oder mehreren Benutzern
<a name="Search"> </a>

Sie können die Ergebnisse einer Suchabfrage verwenden, um Active Directory Benutzer für Skype for Business Server zu konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URIs (Uniform Resource Identifier) nach Benutzern suchen.

Sie können mithilfe der Systemsteuerung von Skype for Business Server oder des Snap-Ins Active Directory Benutzer und Computer nach Benutzern suchen. Im folgenden Verfahren wird beschrieben, wie Sie Skype for Business Server Systemsteuerung verwenden, um nach Benutzern zu suchen.

> [!NOTE]
> In einer Umgebung mit einer zentralen Gesamtstrukturtopologie sind Suchergebnisse möglicherweise nicht genau, wenn Sie nach einem Benutzer durch die e-Mail-Adresse des Benutzers suchen. Stattdessen können Sie Benutzer durch Angabe eines SIP-Adressenpräfixes suchen, z. B. "sip:name", einen Suchfilter hinzufügen und eine SIP-Adresse auswählen, die einen Teil einer E-Mail-Adresse enthält, oder das Cmdlet **Get-CSUser** verwenden.

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen, die SIP-Adresse oder den Anschluss-URI des zu suchenden Benutzerkontos ein, und klicken Sie dann auf **Suchen**.

5. (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse zu beschränken:

   a. Klicken Sie in der oberen rechten Ecke des Bildschirms oberhalb von **Suchergebnisse** auf die Pfeiltaste zum Erweitern des Fensters, und klicken Sie dann auf **Filter hinzufügen**.

   b. Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder auf den Pfeil in der Dropdownliste klicken, um eine Benutzereigenschaft auszuwählen.

   c. Klicken Sie in der Dropdownliste **Gleich** auf **Gleich** oder **Ungleich**.

   d. Geben Sie im Textfeld die Suchkriterien ein, die Sie zum Filtern der Suchergebnisse verwenden möchten, und klicken Sie dann auf **Suchen**.

6. Die Suchergebnisse werden unter **Suchergebnisse** angezeigt. Sie können bestimmte oder alle Benutzer in der Liste auswählen und für die ausgewählten Benutzer Konfigurationsaufgaben durchführen.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Hinzufügen und Aktivieren eines neuen Skype for Business Server Benutzers
<a name="Add"> </a>

Nachdem Sie ein Benutzerkonto in Active Directory Benutzer und Computer aktiviert haben, können Sie Skype for Business Server Systemsteuerung verwenden, um neue Skype for Business Server Benutzerkonten zu erstellen und zu aktivieren, indem Sie Skype for Business Server einen Active Directory Benutzer hinzufügen.

Sie können auch ein Cmdlet verwenden, insbesondere [enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Klicken Sie auf **Benutzer aktivieren**.

5. Klicken Sie im Dialogfeld **neue lync Server Benutzer** auf **Hinzufügen**.

6. Geben Sie im Feld **Benutzer suchen** den vollständigen oder ersten Teil des Namens, des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der e-Mail-Adresse, des Benutzerprinzipalnamens (User Principal Name, UPN) oder der Telefonnummer des gewünschten Active Directory Benutzerkontos ein, und klicken Sie dann auf **Suchen**.

7. Wählen Sie in der Tabelle das Konto aus, das Sie Skype for Business Server hinzufügen möchten, und klicken Sie dann auf **OK**.

8. Weisen Sie den Benutzer einem Pool zu, geben Sie weitere Details an, und weisen Sie die Richtlinien dem gewünschten Benutzer zu, und klicken Sie dann auf **aktivieren**.

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Deaktivieren oder erneutes Aktivieren eines zuvor für Skype for Business Server aktivierten Benutzerkontos
<a name="Disable"> </a>

Mit dem folgenden Verfahren können Sie ein zuvor aktiviertes Benutzerkonto in Skype for Business Server deaktivieren, ohne die Skype for Business Server Einstellungen zu verlieren, die Sie für das Benutzerkonto konfiguriert haben. Da die Skype for Business Server Benutzerkontoeinstellungen nicht verloren gehen, können Sie ein zuvor aktiviertes Benutzerkonto erneut aktivieren, ohne das Benutzerkonto neu konfigurieren zu müssen.

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie auf der linken Navigationsleiste auf **Benutzer**.

4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager, Sicherheitskonto-Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das deaktiviert oder erneut aktiviert werden soll, und klicken Sie dann auf **Suchen**.

5. Klicken Sie in der Tabelle auf das Benutzerkonto, das deaktiviert oder erneut aktiviert werden soll.

6. Führen Sie im Menü **Aktion** einen der folgenden Schritte aus:

   - Wenn Sie das Benutzerkonto für Skype for Business Server vorübergehend deaktivieren möchten, klicken Sie auf **vorübergehend für lync Server deaktivieren**.

   - Klicken Sie zum Aktivieren des Benutzerkontos für Skype for Business Server auf **für lync Server erneut aktivieren**.

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Verwenden von Windows PowerShell zum Deaktivieren oder erneuten Aktivieren von Benutzerkonten

Benutzerkonten können vorübergehend deaktiviert und später erneut aktiviert werden, indem das Cmdlet " **CsUser** " verwendet wird. Sie können dieses Cmdlet entweder über die Skype for Business Server Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Prozess ist in Skype for Business Server identisch.

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

Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) ".

## <a name="disable-a-user-for-enterprise-voice"></a>Deaktivieren eines Benutzers für Enterprise-VoIP
<a name="Disable_EV"> </a>

Verwenden Sie das folgende Verfahren, um Enterprise-VoIP für ein Benutzerkonto zu deaktivieren, das für Skype for Business Server aktiviert ist.

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>So deaktivieren Sie ein Benutzerkonto für Enterprise-VoIP

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.

5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.

6. Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

7. Klicken Sie auf der Seite **Lync Server-Benutzer bearbeiten** unter **Telefonie** auf eine beliebige Option außer **Enterprise-VoIP**.

    > [!NOTE]
    > Klicken Sie unter **Telefonie**auf **Audio/Video deaktiviert**, um zu verhindern, dass ein Benutzer über lync Audio-oder Videoanrufe tätigen kann.

8. Klicken Sie auf **Commit ausführen**.

Der Benutzer kann nun das Enterprise-VoIP-Feature nicht verwenden. Verwandte Informationen: <br/>[Enterprise-VoIP und Mobilität](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype for Business Server-Verwaltungsshell](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Entfernen eines Benutzerkontos mit der Skype for Business Server Management-Shell
<a name="Remove"> </a>

Mit dem folgenden Verfahren können Sie ein zuvor hinzugefügtes Benutzerkonto in Skype for Business Server entfernen.

> [!NOTE]
> Wenn Sie einen Benutzer entfernen, gehen alle Einstellungen verloren, die Sie für das Benutzerkonto konfiguriert haben. Wenn Sie stattdessen ein Benutzerkonto vorübergehend deaktivieren möchten, finden Sie weitere Informationen unter [deaktivieren oder erneutes Aktivieren eines Benutzerkontos, das zuvor für Skype for Business Server aktiviert](user-accounts.md#Disable)wurde.

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie auf der linken Navigationsleiste auf **Benutzer**.

4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager, Sicherheitskonto-Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das deaktiviert oder erneut aktiviert werden soll, und klicken Sie dann auf **Suchen**.

5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie entfernen möchten.

6. Klicken Sie im Menü **Aktion** auf **Aus Lync Server entfernen**. Daraufhin wird ein Dialogfeld angezeigt.

7. Wählen Sie im Dialogfeld**OK** aus, um den Benutzer zu entfernen.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Entfernen von Benutzerkonten mit Windows PowerShell-Cmdlets

Sie können Benutzerkonten mithilfe des Cmdlets Disable-CsUser entfernen. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Prozess ist in Skype for Business Server identisch.

### <a name="to-remove-a-user-account"></a>So entfernen Sie ein Benutzerkonto
Sie können das Cmdlet Disable-CsUser verwenden, um ein Benutzerkonto zu entfernen. Beispiel:

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .

## <a name="see-also"></a>Siehe auch
<a name="Remove"> </a>

[Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)

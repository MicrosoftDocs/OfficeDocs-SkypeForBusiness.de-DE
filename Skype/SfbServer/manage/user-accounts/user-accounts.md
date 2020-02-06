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
description: In den Abschnitten in diesem Artikel wird beschrieben, wie Sie Active Directory-Benutzer in Skype for Business Server aktivieren, vorübergehend deaktivieren oder entfernen.
ms.openlocfilehash: 33af0305fe25b9d7a272e89ae196923e97c4cfd3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817055"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Verwalten von Benutzerkonten für Skype for Business Server

In den Abschnitten in diesem Artikel wird beschrieben, wie Sie Active Directory-Benutzer in Skype for Business Server aktivieren, vorübergehend deaktivieren oder entfernen.

Informationen zum Aktivieren eines Active Directory-Benutzers finden Sie unter [Erstellen eines neuen Benutzerkontos](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx). Informationen zum Löschen eines Active Directory-Benutzers finden Sie unter [Löschen eines Benutzerkontos](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).

Diese Verfahren sollten während eines Wartungsfensters durchgeführt werden, wenn die Nutzung von Skype for Business am niedrigsten ist. Ob dies für einen Tages-oder Wochenplan erfolgt, hängt von den Anforderungen Ihrer Organisation ab.

Dieser Artikel enthält die folgenden Verfahren:

- [So suchen Sie nach einem oder mehreren Benutzern](user-accounts.md#Search)

- [Hinzufügen und Aktivieren eines neuen Skype for Business Server-Benutzers](user-accounts.md#Add)

- [Deaktivieren oder erneutes Aktivieren eines zuvor für Skype for Business Server aktivierten Benutzerkontos](user-accounts.md#Disable)

- [Deaktivieren eines Benutzers für Enterprise-VoIP](user-accounts.md#Disable_EV)

- [Entfernen eines Benutzerkontos mit der Skype for Business Server-Verwaltungsshell](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>So suchen Sie nach einem oder mehreren Benutzern
<a name="Search"> </a>

Sie können die Ergebnisse einer Suchabfrage verwenden, um Active Directory-Benutzer für Skype for Business Server zu konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URI (Uniform Resource Identifier) nach Benutzern suchen.

Sie können über die Skype for Business Server-Systemsteuerung oder das Snap-in Active Directory-Benutzer und-Computer nach Benutzern suchen. Im folgenden Verfahren wird beschrieben, wie Sie mit der Skype for Business Server-Systemsteuerung nach Benutzern suchen können.

> [!NOTE]
> In einer Umgebung mit einer zentralen Gesamtstrukturtopologie sind die Suchergebnisse möglicherweise nicht korrekt, wenn Sie nach einem Benutzer anhand der e-Mail-Adresse des Benutzers suchen. Stattdessen können Sie nach Benutzern suchen, indem Sie ein SIP-Adresspräfix angeben, beispielsweise SIP: Name, einen Suchfilter hinzufügen und eine SIP-Adresse auswählen, die eine teilweise e-Mail-Adresse enthält, oder das Cmdlet " **Get-CSUser** " verwenden.

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Geben Sie im Feld **Benutzer suchen** den gesamten oder den ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens, der SIP-Adresse oder des Leitungs-URIs des Benutzerkontos ein, nach dem Sie suchen möchten, und klicken Sie dann auf **Suchen**.

5. (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:

   a. Klicken Sie in der oberen rechten Ecke des Bildschirms oberhalb der **Suchergebnisse**auf die Schaltfläche zum Erweitern des Pfeils, und klicken Sie dann auf **Filter hinzufügen**.

   b. Geben Sie die Benutzereigenschaft ein, indem Sie Sie eingeben oder in der Dropdownliste auf den Pfeil klicken, um eine Benutzereigenschaft auszuwählen.

   c. Klicken Sie in der Liste **gleich** an auf **gleich** oder **ungleich**.

   d. Geben Sie im Textfeld die Suchkriterien ein, die Sie zum Filtern der Suchergebnisse verwenden möchten, und klicken Sie dann auf **Suchen**.

6. Die Suchergebnisse werden unter **Suchergebnisse**angezeigt. Sie können einen oder alle Benutzer in der Liste auswählen und Konfigurationsaufgaben für die von Ihnen ausgewählten Benutzer durchführen.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Hinzufügen und Aktivieren eines neuen Skype for Business Server-Benutzers
<a name="Add"> </a>

Nachdem Sie ein Benutzerkonto in Active Directory-Benutzer und-Computer aktiviert haben, können Sie die Skype for Business Server-Systemsteuerung verwenden, um neue Skype for Business Server-Benutzerkonten zu erstellen und zu aktivieren, indem Sie einen Active Directory-Benutzer zu Skype for Business Server hinzufügen.

Sie können auch ein Cmdlet verwenden, insbesondere [enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Klicken Sie auf **Benutzer aktivieren**.

5. Klicken Sie im Dialogfeld **neuer lync Server-Benutzer** auf **Hinzufügen**.

6. Geben Sie im Feld Benutzer suchen den gesamten oder den ersten Teil des Namens, den Anzeigenamen, den Vornamen, den **Nachnamen** , den Kontonamen, die e-Mail-Adresse, den Benutzerprinzipalnamen (User Principal Name, UPN) oder die Telefonnummer des gewünschten Active Directory-Benutzerkontos ein, und klicken Sie dann auf **Suchen**.

7. Wählen Sie in der Tabelle das Konto aus, das Sie zu Skype for Business Server hinzufügen möchten, und klicken Sie dann auf **OK**.

8. Weisen Sie den Benutzer einem Pool zu, geben Sie zusätzliche Details an, und weisen Sie die Richtlinien dem gewünschten Benutzer zu, und klicken Sie dann auf **aktivieren**.

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Deaktivieren oder erneutes Aktivieren eines zuvor für Skype for Business Server aktivierten Benutzerkontos
<a name="Disable"> </a>

Mit dem folgenden Verfahren können Sie ein zuvor aktiviertes Benutzerkonto in Skype for Business Server deaktivieren, ohne die Skype for Business-Servereinstellungen zu verlieren, die Sie für das Benutzerkonto konfiguriert haben. Da die Einstellungen für das Skype for Business Server-Benutzerkonto nicht verloren gehen, können Sie ein zuvor aktiviertes Benutzerkonto erneut aktivieren, ohne das Benutzerkonto neu konfigurieren zu müssen.

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Geben Sie im Feld **Benutzer suchen** den gesamten oder den ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontos (Security Accounts Manager), der SIP-Adresse oder des Uniform Resource Identifier (URI) des Benutzerkontos ein, das Sie deaktivieren oder erneut aktivieren möchten, und klicken Sie dann auf **Suchen**.

5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie deaktivieren oder erneut aktivieren möchten.

6. Führen Sie im Menü **Aktion** eine der folgenden Aktionen aus:

   - Wenn Sie das Benutzerkonto für Skype for Business Server vorübergehend deaktivieren möchten, klicken Sie auf **für lync Server vorübergehend deaktivieren**.

   - Wenn Sie das Benutzerkonto für Skype for Business Server aktivieren möchten, klicken Sie auf **für lync Server erneut aktivieren**.

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Verwenden von Windows PowerShell zum Deaktivieren oder erneuten Aktivieren von Benutzerkonten

Mithilfe des Cmdlets " **Satz-CsUser** " können Benutzerkonten vorübergehend deaktiviert und später erneut aktiviert werden. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.

### <a name="to-disable-a-user-account"></a>So deaktivieren Sie ein Benutzerkonto

- Wenn Sie ein Benutzerkonto vorübergehend deaktivieren möchten, legen Sie den Wert der Enabled-Eigenschaft auf false ($false) fest. Beispiel:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>So aktivieren Sie ein Benutzerkonto erneut

- Wenn Sie ein deaktiviertes Benutzerkonto erneut aktivieren möchten, legen Sie den Wert der Enabled-Eigenschaft auf true ($true) fest. Beispiel:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) ".

## <a name="disable-a-user-for-enterprise-voice"></a>Deaktivieren eines Benutzers für Enterprise-VoIP
<a name="Disable_EV"> </a>

Gehen Sie wie folgt vor, um Enterprise-VoIP für ein Benutzerkonto zu deaktivieren, das für Skype for Business Server aktiviert ist.

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>So deaktivieren Sie ein Benutzerkonto für Enterprise-VoIP

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.

5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.

6. Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

7. Klicken Sie auf der Seite **lync Server-Benutzer bearbeiten** unter **Telefonie**auf eine beliebige Option mit Ausnahme von **Enterprise-VoIP**.

    > [!NOTE]
    > Wenn Sie einen Benutzer daran hindern möchten, Audio-oder Videoanrufe mit lync zu führen, klicken Sie unter **Telefonie**auf **Audio/Video deaktiviert**.

8. Klicken Sie auf **Commit ausführen**.

Der Benutzer kann nun die Enterprise-VoIP-Funktion nicht verwenden. Verwandte Informationen: <br/>[Enterprise-VoIP und Mobilität](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype for Business Server-Verwaltungsshell](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Entfernen eines Benutzerkontos mit der Skype for Business Server-Verwaltungsshell
<a name="Remove"> </a>

Sie können das folgende Verfahren verwenden, um ein zuvor hinzugefügtes Benutzerkonto in Skype for Business Server zu entfernen.

> [!NOTE]
> Wenn Sie einen Benutzer entfernen, gehen alle Einstellungen verloren, die Sie für das Benutzerkonto konfiguriert haben. Wenn Sie stattdessen ein Benutzerkonto vorübergehend deaktivieren möchten, lesen Sie [deaktivieren oder erneutes Aktivieren eines zuvor für Skype for Business Server aktivierten Benutzerkontos](user-accounts.md#Disable).

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Geben Sie im Feld **Benutzer suchen** den gesamten oder den ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontos (Security Accounts Manager), der SIP-Adresse oder des Uniform Resource Identifier (URI) des Benutzerkontos ein, das Sie deaktivieren oder erneut aktivieren möchten, und klicken Sie dann auf **Suchen**.

5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie entfernen möchten.

6. Klicken Sie im Menü **Aktion** auf **aus lync Server entfernen**, und es wird ein Dialogfeld angezeigt.

7. Wählen Sie im Dialogfeld **OK** aus, um den Benutzer zu entfernen.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Entfernen von Benutzerkonten mit Windows PowerShell-Cmdlets

Sie können Benutzerkonten mithilfe des Cmdlets Disable-CsUser entfernen. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Windows PowerShell-Remotesitzung ausgeführt werden. Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.

### <a name="to-remove-a-user-account"></a>So entfernen Sie ein Benutzerkonto
Wenn Sie ein Benutzerkonto entfernen möchten, verwenden Sie das Cmdlet Disable-CsUser. Beispiel:

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .

## <a name="see-also"></a>Siehe auch
<a name="Remove"> </a>

[Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[Deaktivieren-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)

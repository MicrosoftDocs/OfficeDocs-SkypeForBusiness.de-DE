---
title: Verwalten von Benutzerkonten für Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: In den Abschnitten in diesem Artikel wird beschrieben, wie aktivieren, vorübergehend deaktivieren oder Entfernen von Active Directory-Benutzer von Skype für Business Server.
ms.openlocfilehash: 2140ae4209e0b91e0d1188a01f96d2d81cac27ef
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214680"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Verwalten von Benutzerkonten für Skype für Business Server

In den Abschnitten in diesem Artikel wird beschrieben, wie aktivieren, vorübergehend deaktivieren oder Entfernen von Active Directory-Benutzer von Skype für Business Server.

Informationen zum Aktivieren von Active Directory-Benutzer finden Sie unter [Erstellen eines neuen Benutzerkontos](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx). Informationen zum Löschen eines Active Directory-Benutzers finden Sie unter [Löschen eines Benutzerkontos](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).

Diese Verfahren sollten während eines Wartungsfensters durchgeführt werden, wenn für die Verwendung von Business Skype niedrigsten ist. Ob dies nach einem Zeitplan täglich oder wöchentlich erfolgt wird durch die Anforderungen Ihrer Organisation bestimmt.

Dieser Artikel enthält die folgenden Verfahren:

- [Suche nach einem oder mehreren Benutzern](user-accounts.md#Search)

- [Fügen Sie hinzu und aktivieren Sie eine neue Skype für Business Server-Benutzer](user-accounts.md#Add)

- [Deaktivieren oder Reaktivieren eines Benutzerkontos, die zuvor für die Skype für Business Server aktiviert](user-accounts.md#Disable)

- [Deaktivieren eines Benutzers für Enterprise-VoIP](user-accounts.md#Disable_EV)

- [Entfernen eines Benutzerkontos mit der Skype für Business Server-Verwaltungsshell](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>Suche nach einem oder mehreren Benutzern
<a name="Search"> </a>

Sie können die Ergebnisse einer Suchabfrage verwenden, Active Directory-Benutzer für Skype für Business Server konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URI (Uniform Resource Identifier) nach Benutzern suchen.

Sie können nach Benutzern suchen, unter Verwendung der Skype für Business Server-Systemsteuerung oder Active Directory-Benutzer und Computer-Snap-in. Das folgende Verfahren beschreibt, wie Sie Skype Business Server-Systemsteuerung verwenden, um nach Benutzern suchen.

> [!NOTE]
> In einer Umgebung mit einer Topologie mit zentraler Gesamtstruktur möglicherweise Suchergebnisse nicht genau sein, wenn Sie für einen Benutzer von e-Mail-Adresse des Benutzers suchen. Sie können stattdessen durch Angeben einer SIP-Adresspräfix, z. B.: Namen der Sip-Benutzern suchen, fügen Sie einen Filter für die Suche und wählen Sie eine SIP-Adresse, die eine partielle e-Mail-Adresse enthält oder verwenden Sie das Cmdlet **Get-CSUser** .

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Klicken Sie in das Feld **Suchbenutzer** alle oder den ersten Teil der Anzeigename, Vorname, Nachname, SAM-Kontoname SIP-Adresse oder Anschluss-URI des Benutzerkontos, dem Sie suchen, und klicken Sie dann auf **Suchen**möchten.

5. (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:

   a. Klicken Sie auf die Schaltfläche in der oberen rechten Ecke des Bildschirms oberhalb **von Suchergebnisse**Pfeil, und klicken Sie dann auf **Filter hinzufügen**.

   b. Geben Sie die Benutzereigenschaft durch eingeben oder auf den Pfeil in der Dropdownliste aus, um eine Benutzereigenschaft auszuwählen.

   c. Klicken Sie in der Liste **gleich** auf **gleich** oder **ungleich**.

   d. Klicken Sie in das Textfeld Geben Sie die Suchkriterien ein, den, die Sie verwenden, um die Suchergebnisse filtern möchten, und klicken Sie dann auf **Suchen**.

6. Die Suchergebnisse werden unter **Suchergebnisse**angezeigt. Sie können einige oder alle Benutzer in der Liste wählen, und führen Konfigurationsaufgaben für die Benutzer, die Sie auswählen.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Fügen Sie hinzu und aktivieren Sie eine neue Skype für Business Server-Benutzer
<a name="Add"> </a>

Nach dem Aktivieren eines Benutzerkontos in Active Directory-Benutzer und-Computer, können Sie Skype Business Server-Systemsteuerung erstellen und Aktivieren von neuen Skype für Benutzerkonten Business Server Skype für Business Server einen Active Directory-Benutzer hinzufügen.

Sie können auch auf einem speziell [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)-Cmdlet verwenden.

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Klicken Sie auf **Benutzer aktivieren**.

5. Klicken Sie auf **Hinzufügen**, klicken Sie im Dialogfeld **Neuer Lync Server-Benutzer** .

6. Geben Sie im Feld **Suche Benutzer** alle den ersten Teil des Namens anzeigen Sie, Name, Vorname, Nachname, Kontonamen Sicherheitskontenverwaltung (SAM), e-Mail-Adresse, User Principal Name (UPN) oder des Active Directory-Benutzerkontos die gewünschte Telefonnummer , und klicken Sie dann auf **Suchen**.

7. Wählen Sie in der Tabelle das Konto aus, den, das Sie Skype für Business Server hinzufügen möchten, und klicken Sie dann auf **OK**.

8. Weisen Sie dem Benutzer zu einem Pool, geben Sie zusätzliche Details, und weisen Sie die Richtlinien für den gewünschten Benutzer, und klicken Sie dann auf **Aktivieren**.

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Deaktivieren oder Reaktivieren eines Benutzerkontos, die zuvor für die Skype für Business Server aktiviert
<a name="Disable"> </a>

Das folgende Verfahren können Sie ein zuvor aktiviertes Benutzerkonto in Skype für Business Server deaktivieren, ohne zu verlieren die Skype für Business Server-Einstellungen, die Sie für das Benutzerkonto konfiguriert. Da Sie nicht die Skype für Business Server Benutzerkonteneinstellungen verlieren, können Sie ein zuvor aktiviertes Benutzerkonto erneut erneut ermöglichen, ohne dass das Benutzerkonto neu konfigurieren.

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Geben Sie im Feld **Suche Benutzer** alle den ersten Teil der Anzeigename, Vorname, Nachname, Kontonamen Sicherheitskontenverwaltung (SAM), SIP-Adresse oder Zeile URI Uniform Resource Identifier () des Benutzerkontos, das Sie deaktivieren oder aktivieren möchten, und klicken Sie dann auf **Suchen**.

5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie deaktivieren oder aktivieren möchten.

6. Klicken Sie im Menü **Aktion** auf führen Sie eine der folgenden Aktionen aus:

   - Um das Benutzerkonto vorübergehend für Skype für Business Server deaktivieren, klicken Sie auf **vorübergehend für Lync Server deaktivieren**.

   - Klicken Sie auf **erneut für Lync Server aktivieren**, um das Benutzerkonto für Skype für Business Server zu aktivieren.

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Deaktivieren oder Reaktivieren von Benutzerkonten mithilfe von Windows Powershell

Benutzerkonten können vorübergehend deaktiviert, und klicken Sie dann später wieder aktiviert, mit dem **Set-CsUser** -Cmdlet. Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Windows PowerShell ausführen. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype für Business Server identisch.

### <a name="to-disable-a-user-account"></a>So deaktivieren Sie ein Benutzerkonto

- Legen Sie den Wert der Eigenschaft Enabled auf "false" ($False), um ein Benutzerkonto vorübergehend zu deaktivieren. Beispiel:

  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>Reaktivieren ein Benutzerkontos

- Um ein deaktiviertes Benutzerkonto wieder zu aktivieren, legen Sie den Wert der Eigenschaft Enabled auf "true" ($True). Beispiel:

  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Weitere Informationen finden Sie im Hilfethema zum [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) -Cmdlet.

## <a name="disable-a-user-for-enterprise-voice"></a>Deaktivieren eines Benutzers für Enterprise-VoIP
<a name="Disable_EV"> </a>

Verwenden Sie das folgende Verfahren, um Enterprise-VoIP für ein Benutzerkonto deaktivieren, die für Skype für Business Server aktiviert ist.

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>So deaktivieren Sie ein Benutzerkonto für Enterprise-VoIP

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.

5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.

6. Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

7. Klicken Sie auf der Seite **Lync Server-Benutzer bearbeiten** unter **Telefonie**auf eine beliebige Option außer **Enterprise-VoIP**.

    > [!NOTE]
    > Um einen Benutzer daran zu hindern, Ausführen von Audio-oder Videoanrufe mit Lync, klicken Sie unter **Telefonie**, klicken Sie auf **Audio/Video deaktiviert**.

8. Klicken Sie auf **Commit ausführen**.

Der Benutzer kann jetzt das Enterprise-VoIP-Feature verwenden. Verwandte Informationen: <br/>[Enterprise-VoIP und Mobilität](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [Aktivieren von Benutzern für Enterprise-VoIP in Skype für Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype for Business Server-Verwaltungsshell](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Entfernen eines Benutzerkontos mit der Skype für Business Server-Verwaltungsshell
<a name="Remove"> </a>

Das folgende Verfahren können Sie um ein zuvor hinzugefügtes Benutzerkonto in Skype für Business Server zu entfernen.

> [!NOTE]
> Entfernen eines Benutzers führen Sie alle Einstellungen, die Sie für das Benutzerkonto konfiguriert haben, gehen verloren. Wenn Sie stattdessen ein Benutzerkonto vorübergehend deaktivieren möchten, finden Sie unter [deaktivieren oder reaktivieren ein Benutzerkontos, die zuvor für die Skype für Business Server aktiviert](user-accounts.md#Disable).

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4. Geben Sie im Feld **Suche Benutzer** alle den ersten Teil der Anzeigename, Vorname, Nachname, Kontonamen Sicherheitskontenverwaltung (SAM), SIP-Adresse oder Zeile URI Uniform Resource Identifier () des Benutzerkontos, das Sie deaktivieren oder aktivieren möchten, und klicken Sie dann auf **Suchen**.

5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie entfernen möchten.

6. Das wird auf **das Aktionsmenü** , select **Entfernen von Lync Server**und ein Dialogfeld angezeigt.

7. Wählen Sie im Dialogfeld **OK** , um den Benutzer zu entfernen.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Entfernen von Benutzerkonten mit Windows Powershell-cmdlets

Sie können Benutzerkonten mit dem Cmdlet Disable-CsUser entfernen. Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer Windows PowerShell-Remotesitzung ausgeführt werden. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype für Business Server identisch.

### <a name="to-remove-a-user-account"></a>Zum Entfernen eines Benutzerkontos
Um ein Benutzerkonto zu entfernen, verwenden Sie das Cmdlet Disable-CsUser. Beispiel:

  ```
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

Weitere Informationen finden Sie im Hilfethema für das Cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .

## <a name="see-also"></a>Siehe auch
<a name="Remove"> </a>

[Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)

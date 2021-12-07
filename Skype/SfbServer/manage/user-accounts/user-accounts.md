---
title: Verwalten von Benutzerkonten für Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: In den Abschnitten in diesem Artikel wird beschrieben, wie Active Directory-Benutzer aus Skype for Business Server aktiviert, vorübergehend deaktiviert oder entfernt werden.
ms.openlocfilehash: 39016a83c11553cd39448efa34d61ffbba5045e9
ms.sourcegitcommit: 2aae13454178dc2e2cbc8cca967cd181c5f9d044
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/06/2021
ms.locfileid: "61314213"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Verwalten von Benutzerkonten für Skype for Business Server

In den Abschnitten in diesem Artikel wird beschrieben, wie Active Directory-Benutzer aus Skype for Business Server aktiviert, vorübergehend deaktiviert oder entfernt werden.

Informationen zum Aktivieren eines Active Directory-Benutzers finden Sie unter ["Erstellen eines neuen Benutzerkontos".](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)) Informationen zum Löschen eines Active Directory-Benutzers finden Sie unter [Löschen eines Benutzerkontos.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))

Diese Verfahren sollten während eines Wartungsfensters ausgeführt werden, wenn Skype for Business Nutzung am niedrigsten ist. Ob dies nach einem täglichen oder wöchentlichen Zeitplan erfolgt, hängt von den Anforderungen Ihrer Organisation ab.

Dieser Artikel enthält die folgenden Verfahren:

- [Suchen nach einem oder mehreren Benutzern](#search-for-one-or-more-users)

- [Hinzufügen und Aktivieren eines neuen Skype for Business Server Benutzers](#add-and-enable-a-new-skype-for-business-server-user)

- [Deaktivieren oder erneutes Aktivieren eines Benutzerkontos für Skype for Business Server](#disable-or-re-enable-a-user-account-for-skype-for-business-server)

- [Deaktivieren eines Benutzers für Enterprise-VoIP](#disable-a-user-for-enterprise-voice)

- [Entfernen eines Benutzerkontos mit der Skype for Business Server-Verwaltungsshell](#remove-a-user-account-with-the-skype-for-business-server-management-shell)

## <a name="search-for-one-or-more-users"></a>Suchen nach einem oder mehreren Benutzern

Sie können die Ergebnisse einer Suchabfrage verwenden, um Active Directory-Benutzer für Skype for Business Server zu konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URIs (Uniform Resource Identifier) nach Benutzern suchen.

Sie können nach Benutzern suchen, indem Sie die Skype for Business Server Systemsteuerung oder das Snap-In "Active Directory-Benutzer und -Computer" verwenden. Im folgenden Verfahren wird beschrieben, wie Sie Skype for Business Server Systemsteuerung verwenden, um nach Benutzern zu suchen.

> [!NOTE]
> In einer Umgebung mit einer zentralen Gesamtstrukturtopologie sind die Suchergebnisse möglicherweise nicht genau, wenn Sie anhand der E-Mail-Adresse des Benutzers nach einem Benutzer suchen. Stattdessen können Sie Benutzer durch Angabe eines SIP-Adressenpräfixes suchen, z. B. "sip:name", einen Suchfilter hinzufügen und eine SIP-Adresse auswählen, die einen Teil einer E-Mail-Adresse enthält, oder das Cmdlet **Get-CSUser** verwenden.

### <a name="search-for-users-using-the-new-control-panel"></a>Suchen nach Benutzern mithilfe der neuen Systemsteuerung 

1. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.
 
2. Melden Sie sich mit einem Benutzerkonto an, das der Rolle "CsUserAdministrator" oder der Rolle "CsAdministrator" zugewiesen ist.

3. Wählen Sie im linken Bereich **Benutzer** aus.

4. Geben Sie auf der Seite **"Benutzer"** im **Suchfeld** den gesamten oder den ersten Teil des Anzeigenamens ein, nach dem Sie suchen möchten, und drücken Sie die **EINGABETASTE.**

5. (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse zu beschränken:

    1. Klicken Sie auf die Filterschaltfläche neben dem **Suchfeld.**

    2. Wählen Sie im angezeigten **Filterbereich** die erforderliche Benutzereigenschaft aus, indem Sie auf den Pfeil in der Dropdownliste klicken.

    3. Klicken Sie auf den Pfeil in der Dropdown-Operatorliste, um den erforderlichen Operator auszuwählen.

    4. Geben Sie im Textfeld die Suchkriterien ein, die Sie zum Filtern von Suchergebnissen verwenden möchten, und klicken Sie dann auf **OK.**

6. Die Suchergebnisse werden auf der Seite **"Benutzer"** angezeigt. Sie können bestimmte oder alle Benutzer in der Liste auswählen und für die ausgewählten Benutzer Konfigurationsaufgaben durchführen.

> [!NOTE]
> Die neue Systemsteuerung ist für Skype for Business Server 2015 nicht verfügbar.

### <a name="search-for-users-using-the-legacy-control-panel"></a>Suchen nach Benutzern mithilfe der älteren Systemsteuerung 

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.

3. Wählen Sie im linken Bereich **Benutzer** aus.

4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen, die SIP-Adresse oder den Anschluss-URI des zu suchenden Benutzerkontos ein, und klicken Sie dann auf **Suchen**.

5. (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse zu beschränken:

    1. Klicken Sie in der oberen rechten Ecke des Bildschirms oberhalb von **Suchergebnisse** auf die Pfeiltaste zum Erweitern des Fensters, und klicken Sie dann auf **Filter hinzufügen**.

    2. Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder in der Dropdownliste auf den Pfeil klicken, um eine Benutzereigenschaft auszuwählen.

    3. Wählen Sie in der Liste **"Gleich" die** Option **"Gleich"** oder **"Nicht gleich" aus.**

    4. Geben Sie im Textfeld die Suchkriterien ein, die Sie zum Filtern der Suchergebnisse verwenden möchten, und klicken Sie dann auf **Suchen**.

6. Die Suchergebnisse werden unter **Suchergebnisse** angezeigt. Sie können bestimmte oder alle Benutzer in der Liste auswählen und für die ausgewählten Benutzer Konfigurationsaufgaben durchführen.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Hinzufügen und Aktivieren eines neuen Skype for Business Server Benutzers

Nachdem Sie ein Benutzerkonto in Active Directory-Benutzern und -Computern aktiviert haben, können Sie Skype for Business Server Systemsteuerung verwenden, um neue Skype for Business Server Benutzerkonten zu erstellen und zu aktivieren, indem Sie einen Active Directory-Benutzer zu Skype for Business Server hinzufügen.

Sie können auch ein Cmdlet verwenden, insbesondere [Enable-CsUser.](/powershell/module/skype/enable-csuser)

### <a name="add-a-user-using-the-new-control-panel"></a>Hinzufügen eines Benutzers mithilfe der neuen Systemsteuerung 

1. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.
 
2. Melden Sie sich mit einem Benutzerkonto an, das der Rolle "CsUserAdministrator" oder der Rolle "CsAdministrator" zugewiesen ist.

3. Navigieren Sie zu  >  **"Benutzer aktivieren"** und klicken Sie auf **"Hinzufügen".**

4. Geben Sie im **Suchfeld** den gesamten oder den ersten Teil des Anzeigenamens ein, und klicken Sie auf **"Suchen".**

5. (Optional) Um zusätzliche Benutzerkriterien anzugeben, klicken Sie auf **+Filter hinzufügen,** wählen Sie die erforderliche Benutzereigenschaft aus, wählen Sie den Operator aus, und geben Sie den Wert ein. Klicken Sie auf **Suchen**.

6. Wählen Sie in der Tabelle das Konto aus, das Sie Skype for Business Server hinzufügen möchten, und klicken Sie dann auf **OK.**

7. Weisen Sie den Benutzer einem Pool zu, geben Sie zusätzliche Details an, weisen Sie dem Benutzer die erforderlichen Richtlinien zu, und klicken Sie dann auf **"Aktivieren".**

> [!NOTE]
> Die neue Systemsteuerung ist für Skype for Business Server 2015 nicht verfügbar.

### <a name="add-a-user-using-the-legacy-control-panel"></a>Hinzufügen eines Benutzers mithilfe der älteren Systemsteuerung 

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.

3. Navigieren Sie zu **"Benutzer**  >  **aktivieren"**  >  **"Neuer Lync Server-Benutzer",** und klicken Sie auf **"Hinzufügen".**

6. Geben Sie im Feld **"Benutzer suchen"** den namen, den Anzeigenamen, den Vornamen, den Nachnamen, den SAM-Kontonamen (Security Accounts Manager), die E-Mail-Adresse, den Benutzerprinzipalnamen (UPN) oder die Telefonnummer des gewünschten Active Directory-Benutzerkontos ein, und klicken Sie dann auf **"Suchen".**

7. Wählen Sie in der Tabelle das Konto aus, das Sie Skype for Business Server hinzufügen möchten, und klicken Sie dann auf **OK.**

8. Weisen Sie den Benutzer einem Pool zu, geben Sie zusätzliche Details an, weisen Sie die Richtlinien dem gewünschten Benutzer zu, und klicken Sie dann auf **"Aktivieren".**

## <a name="disable-or-re-enable-a-user-account-for-skype-for-business-server"></a>Deaktivieren oder erneutes Aktivieren eines Benutzerkontos für Skype for Business Server

Sie können das folgende Verfahren verwenden, um ein zuvor aktiviertes Benutzerkonto in Skype for Business Server zu deaktivieren, ohne die Skype for Business Server Einstellungen zu verlieren, die Sie für das Benutzerkonto konfiguriert haben. Da Sie die Skype for Business Server Benutzerkontoeinstellungen nicht verlieren, können Sie ein zuvor aktiviertes Benutzerkonto erneut aktivieren, ohne das Benutzerkonto neu konfigurieren zu müssen.

### <a name="disable-or-re-enable-a-user-account-using-the-new-control-panel"></a>Deaktivieren oder erneutes Aktivieren eines Benutzerkontos mithilfe der neuen Systemsteuerung

1. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.
 
2. Melden Sie sich mit einem Benutzerkonto an, das der Rolle "CsUserAdministrator" oder der Rolle "CsAdministrator" zugewiesen ist.

3. Wählen Sie im linken Bereich **Benutzer** aus.

4. Geben Sie auf der Seite **"Benutzer"** im **Suchfeld** den gesamten oder den ersten Teil des Anzeigenamens ein, und drücken Sie die **EINGABETASTE.**

5. Doppelklicken Sie in der Tabelle auf das Benutzerkonto, das Sie deaktivieren oder erneut aktivieren möchten.
    1. In the panel that appears, to temporarily disable the user account for Skype for Business Server, select **Disable User**. Klicken Sie im angezeigten Bereich auf **"Speichern".**
    2. Um das Benutzerkonto für Skype for Business Server erneut zu aktivieren, wählen Sie im Bereich **"Benutzer erneut aktivieren"** aus. Klicken Sie im nächsten angezeigten Bereich auf **"Speichern".**

> [!NOTE]
> Die neue Systemsteuerung ist für Skype for Business Server 2015 nicht verfügbar.

### <a name="disable-or-re-enable-a-user-account-using-the-legacy-control-panel"></a>Deaktivieren oder erneutes Aktivieren eines Benutzerkontos mithilfe der älteren Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.

3. Wählen Sie im linken Bereich **Benutzer** aus.

4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das deaktiviert oder erneut aktiviert werden soll, und klicken Sie dann auf **Suchen**.

5. Klicken Sie in der Tabelle auf das Benutzerkonto, das deaktiviert oder erneut aktiviert werden soll.

6. Führen Sie im Menü **Aktion** einen der folgenden Schritte aus:
   1. Um das Benutzerkonto für Skype for Business Server vorübergehend zu deaktivieren, wählen Sie **für Lync Server vorübergehend deaktivieren** aus.
   2. Um das Benutzerkonto für Skype for Business Server zu aktivieren, wählen Sie **für Lync Server erneut aktivieren** aus.
  
### <a name="disable-or-re-enable-user-accounts-using-windows-powershell"></a>Deaktivieren oder erneutes Aktivieren von Benutzerkonten mit Windows PowerShell

Benutzerkonten können mithilfe des Cmdlets **"Set-CsUser"** vorübergehend deaktiviert und später wieder aktiviert werden. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie unter [Microsoft Lync Remote PowerShell Administration.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) Der Vorgang ist in Skype for Business Server identisch.

### <a name="to-disable-a-user-account-using-windows-powershell"></a>So deaktivieren Sie ein Benutzerkonto mit Windows PowerShell

- Um ein Benutzerkonto vorübergehend zu deaktivieren, legen Sie den Wert der aktivierten Eigenschaft auf "False" ($False) fest. Beispiel:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account-using-windows-powershell"></a>So aktivieren Sie ein Benutzerkonto mit Windows PowerShell

- Um ein deaktiviertes Benutzerkonto erneut zu aktivieren, legen Sie den Wert der aktivierten Eigenschaft auf "True" ($True) fest. Beispiel:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Set-CsUser".](/powershell/module/skype/set-csuser)

## <a name="disable-a-user-for-enterprise-voice"></a>Deaktivieren eines Benutzers für Enterprise-VoIP

Verwenden Sie das folgende Verfahren, um Enterprise-VoIP für ein Benutzerkonto zu deaktivieren, das für Skype for Business Server aktiviert ist.

### <a name="disable-a-user-for-enterprise-voice-using-new-control-panel"></a>Deaktivieren eines Benutzers für Enterprise-VoIP mithilfe der neuen Systemsteuerung

1. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.
 
2. Melden Sie sich mit einem Benutzerkonto an, das der Rolle "CsUserAdministrator" oder der Rolle "CsAdministrator" zugewiesen ist.

3. Klicken Sie im linken Bereich auf **"Benutzer".**

4. Geben Sie im **Suchfeld** den gesamten oder den ersten Teil des Anzeigenamens ein, und klicken Sie auf **"Suchen".**

5. Doppelklicken Sie in der Tabelle auf das Benutzerkonto, das Sie für Enterprise-VoIP deaktivieren möchten.

6. Klicken Sie in dem angezeigten Bereich auf das Stiftsymbol neben **"Zugewiesene Richtlinien".**

7. Klicken Sie im Bereich **"Zugewiesene Richtlinien"** unter **"Telefonie"** auf eine beliebige Option außer **Enterprise-VoIP** in der Dropdownliste.

8. Klicken Sie auf **Speichern**.

    > [!NOTE]
    > Klicken Sie unter **"Telefonie"** auf **"Audio/Video" deaktiviert,** um zu verhindern, dass ein Benutzer Audio- oder Videoanrufe tätigen kann.

Der Benutzer kann das feature Enterprise-VoIP jetzt nicht mehr verwenden. 

> [!NOTE]
> Die neue Systemsteuerung ist für Skype for Business Server 2015 nicht verfügbar.

### <a name="disable-a-user-account-for-enterprise-voice-using-legacy-control-panel"></a>Deaktivieren eines Benutzerkontos für Enterprise-VoIP mithilfe der älteren Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.

3. Klicken Sie im linken Bereich auf **"Benutzer".**

4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.

5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.

6. Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

7. Klicken Sie auf der Seite **Lync Server-Benutzer bearbeiten** unter **Telefonie** auf eine beliebige Option außer **Enterprise-VoIP**.

    > [!NOTE]
    > Klicken Sie unter **"Telefonie"** auf **"Audio/Video deaktiviert",** um zu verhindern, dass ein Benutzer Audio- oder Videoanrufe über Lync tätigen kann.

8. Klicken Sie auf **Commit ausführen**.

Der Benutzer kann das feature Enterprise-VoIP jetzt nicht mehr verwenden.

Verwandte Informationen: <br/>[Enterprise-VoIP und Mobilität](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype for Business Server-Verwaltungsshell](../management-shell.md)

## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Entfernen eines Benutzerkontos mit der Skype for Business Server-Verwaltungsshell

Mit dem folgenden Verfahren können Sie ein zuvor hinzugefügtes Benutzerkonto in Skype for Business Server entfernen.

> [!NOTE]
> Wenn Sie einen Benutzer entfernen, gehen alle Einstellungen verloren, die Sie für das Benutzerkonto konfiguriert haben. Wenn Sie stattdessen ein Benutzerkonto vorübergehend deaktivieren möchten, lesen [Sie "Deaktivieren oder erneutes Aktivieren eines Benutzerkontos, das zuvor für Skype for Business Server aktiviert war".](#disable-or-re-enable-a-user-account-for-skype-for-business-server)

### <a name="remove-a-user-using-the-new-control-panel"></a>Entfernen eines Benutzers mithilfe der neuen Systemsteuerung

1. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.
 
2. Melden Sie sich mit einem Benutzerkonto an, das der Rolle "CsUserAdministrator" oder der Rolle "CsAdministrator" zugewiesen ist.

3. Wählen Sie im linken Bereich **Benutzer** aus.

4. Geben Sie im **Suchfeld** den gesamten oder den ersten Teil des Anzeigenamens ein, und klicken Sie auf **"Suchen".**

5. Doppelklicken Sie in der Tabelle auf das Benutzerkonto, das Sie entfernen möchten.

6. Klicken Sie im angezeigten Bereich auf **"Benutzer entfernen".** Klicken Sie im nächsten angezeigten Bereich auf **"OK".**

> [!NOTE]
> Die neue Systemsteuerung ist für Skype for Business Server 2015 nicht verfügbar.

### <a name="remove-a-user-using-the-legacy-control-panel"></a>Entfernen eines Benutzers mithilfe der älteren Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.

3. Wählen Sie im linken Bereich **Benutzer** aus.

4. Geben Sie im Feld **"Benutzer suchen"** den gesamten oder den ersten Teil des Anzeigenamens, Vornamens, Nachnamens, SAM-Kontonamens (Security Accounts Manager), SIP-Adresse oder URI (Line Uniform Resource Identifier) des Benutzerkontos ein, das Sie entfernen möchten, und klicken Sie dann auf **Suchen**.

5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie entfernen möchten.

6. Klicken Sie im Menü **Aktion** auf **Aus Lync Server entfernen**. Daraufhin wird ein Dialogfeld angezeigt.

7. Wählen Sie im Dialogfeld **OK** aus, um den Benutzer zu entfernen.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Entfernen von Benutzerkonten mit Windows PowerShell Cmdlets

Sie können Benutzerkonten mithilfe des Cmdlets Disable-CsUser entfernen. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie unter [Microsoft Lync Remote PowerShell Administration.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) Der Vorgang ist in Skype for Business Server identisch.

Sie können das Cmdlet Disable-CsUser verwenden, um ein Benutzerkonto zu entfernen. Beispiel:

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

Nachdem dieser Befehl ausgeführt wurde, gibt es keine Möglichkeit, das Konto erneut zu aktivieren und die vorherigen Kontoeinstellungen wiederherzustellen. Stattdessen müssen Sie das Cmdlet Enable-CsUser- verwenden, um für Ken Myer ein ganz neues Konto zu erstellen.

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Disable-CsUser".](/powershell/module/skype/disable-csuser)

## <a name="see-also"></a>Siehe auch

[Enable-CsUser](/powershell/module/skype/enable-csuser)

[Disable-CsUser](/powershell/module/skype/disable-csuser)

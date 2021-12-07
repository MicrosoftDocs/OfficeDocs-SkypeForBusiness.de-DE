---
title: Anpassen von Benutzerkontoeigenschaften für Skype for Business Server
ms.reviewer: ''
ms.author: v-mathavale
author: v-mathavale
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Mithilfe der Verfahren in diesem Abschnitt können Sie einzelne Benutzerkontoeigenschaften ändern.
ms.openlocfilehash: f80847b57122539654541a444f427f4031ee6197
ms.sourcegitcommit: 2aae13454178dc2e2cbc8cca967cd181c5f9d044
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/06/2021
ms.locfileid: "61314203"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>Anpassen von Benutzerkontoeigenschaften für Skype for Business Server
 
Mithilfe der Verfahren in diesem Abschnitt können Sie einzelne Benutzerkontoeigenschaften ändern.
 
Es gibt zwei grundlegende Vorgänge, die auf der Ebene einzelner Benutzer ausgeführt werden können:
 
- [Konfigurieren von Telefonieoptionen für ein bestimmtes Benutzerkonto](#configure-telephony-options-for-a-specific-user-account)

- [Verschieben von Benutzern in einen anderen Pool](#move-users-to-another-pool)
 
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Konfigurieren von Telefonieoptionen für ein bestimmtes Benutzerkonto

Sie können die Telefonieeinstellungen für einen bestimmten Benutzer anpassen (sofern der einzelne Benutzer für Skype for Business Server aktiviert wurde und die Organisation die Telefonie unterstützt).
 
Skype for Business Server Telefonieoptionen für Benutzer umfassen Folgendes:
 
|Telefonieoptionen  |Beschreibung  |
|---------|---------|
|**Audio/Video deaktiviert**|Der Benutzer kann keine Anrufe mit Audio und Video tätigen.|
|**Nur PC zu PC** | Der Benutzer kann nur Audio- oder Videoanrufe von PC zu PC tätigen.|
|**Enterprise-VoIP** | Der Benutzer kann die Skype for Business Server Infrastruktur verwenden, um alle eingehenden und ausgehenden Anrufe weiterzuleiten. Außerdem kann der Benutzer Anrufe von PC zu PC tätigen.|
|**Remoteanrufsteuerung**   | Der Benutzer kann Skype for Business Server verwenden, um das Desktoptelefon zu steuern, und auch PC-zu-PC-Anrufe tätigen.|
 
Ausführliche Informationen zum Konfigurieren der Telefonie für eine Organisation finden Sie unter Aktivieren von [Benutzern für Enterprise-VoIP in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) und Bereitstellen von Enterprise-VoIP in [Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in der Bereitstellungsdokumentation.
 
### <a name="configure-telephony-options-for-specific-users-using-new-control-panel"></a>Konfigurieren von Telefonieoptionen für bestimmte Benutzer mithilfe der neuen Systemsteuerung 
 
1. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.
 
2. Melden Sie sich mit einem Benutzerkonto an, das der Rolle "CsUserAdministrator" oder der Rolle "CsAdministrator" zugewiesen ist.
 
3. Wählen Sie im linken Bereich **Benutzer** aus.
 
4. Geben Sie im **Suchfeld** den gesamten oder den ersten Teil des Anzeigenamens ein, und klicken Sie auf **"Suchen".**
 
5. Doppelklicken Sie in der Tabelle auf das Benutzerkonto, das Sie ändern möchten.
 
6. Klicken Sie in dem angezeigten Bereich auf das Stiftsymbol neben **"Zugewiesene Richtlinien".**
 
7. Führen Sie im Dialogfeld **Telefonie** die folgenden Schritte aus:
 
    1. Um Audio- und Videoanrufe für den Benutzer zu deaktivieren, wählen Sie **"Audio/Video"** in der Dropdownliste deaktiviert aus.
 
    2. Um die PC-zu-PC-Audiokommunikation für den Benutzer zu aktivieren, jedoch keine Remoteanrufsteuerung oder Enterprise-VoIP, wählen Sie **PC-zu-PC nur** in der Dropdownliste aus. Geben Sie einen Wert für **Anschluss-URI** für das Telefon an, das der Benutzer für die Audiokommunikation von PC zu PC verwendet.
 
    3. **Wählen** Sie Enterprise-VoIP in der Dropdownliste aus, um die Telefonanrufe des Benutzers mithilfe der Skype for Business Infrastruktur gemäß der Dienstrichtlinie weiterzuleiten, einschließlich PC-zu-PC-Audiokommunikation. Geben Sie unter **Anschluss-URI** die Telefonnummer für Enterprise-VoIP an. Geben Sie unter **Richtlinie für Wähleinstellungen** und **VoIP-Richtlinie** die entsprechenden Richtlinien für den Benutzer an. Um die Normalisierungsregeln für die Übersetzung von vom Benutzer gewählten Telefonnummern in das E.164-Format anzugeben, wählen Sie das entsprechende Standortprofil in der Dropdownliste der **Standortrichtlinie** aus.
 
    4. Um die Remoteanrufsteuerung zu aktivieren, mit der Benutzer ihre Desktoptelefonleitung von Skype for Business Server zum Tätigen von PC-zu-PC-Anrufen und PC-zu-Telefonanrufen steuern können, wählen Sie in der Dropdownliste die **Remoteanrufsteuerung** aus. Geben Sie im **Anschluss-URI** die Telefonnummer für die Remoteanrufsteuerung an. Der Benutzer muss über eine Desktoptelefon- und NEBENSTELLEN-Verbindung (Private Branch Exchange) für die Anrufweiterleitung verfügen.

> [!NOTE]
> Die neue Systemsteuerung ist für Skype for Business Server 2015 nicht verfügbar.

### <a name="configure-telephony-options-for-specific-users-using-legacy-control-panel"></a>Konfigurieren von Telefonieoptionen für bestimmte Benutzer mithilfe der älteren Systemsteuerung
 
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
 
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
 
3. Wählen Sie im linken Bereich **Benutzer** aus.
 
4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **Suchen**.
 
5. Wählen Sie in der Tabelle das Benutzerkonto aus, das Sie ändern möchten.
 
6. Wählen Sie im Menü **Bearbeiten** die Option **Ändern** aus.
 
7. Führen Sie im Dialogfeld **Telefonie** die folgenden Schritte aus:
 
    1. Um Audio- und Videoanrufe für den Benutzer zu deaktivieren, wählen Sie **"Audio/Video" deaktiviert** aus.
 
    2. Um die PC-zu-PC-Audiokommunikation für den Benutzer zu aktivieren, jedoch keine Remoteanrufsteuerung oder Enterprise-VoIP, wählen Sie **nur PC-zu-PC aus.** Geben Sie einen Wert für **Anschluss-URI** für das Telefon an, das der Benutzer für die Audiokommunikation von PC zu PC verwendet.
 
    3. Um die Telefonanrufe des Benutzers mithilfe der Skype for Business Infrastruktur gemäß der Dienstrichtlinie weiterzuleiten, einschließlich pc-zu-PC-Audiokommunikation, wählen Sie **Enterprise-VoIP** aus. Geben Sie unter **Anschluss-URI** die Telefonnummer für Enterprise-VoIP an. Geben Sie unter **Richtlinie für Wähleinstellungen** und **VoIP-Richtlinie** die entsprechenden Richtlinien für den Benutzer an. Wählen Sie unter **Ortungsrichtlinie** das angemessene Standortprofil aus, um die Normalisierungsregeln für die Übersetzung der vom Benutzer gewählten Telefonnummern in das E.164-Format anzugeben.
 
    4. Um die Remoteanrufsteuerung zu aktivieren, mit der Benutzer ihre Desktoptelefonleitung von Skype for Business Server zum Tätigen von PC-zu-PC-Anrufen und PC-zu-Telefonanrufen steuern können, wählen Sie **Remoteanrufsteuerung** aus. Geben Sie im **Anschluss-URI** die Telefonnummer für die Remoteanrufsteuerung an. Der Benutzer muss über eine Desktoptelefon- und NEBENSTELLEN-Verbindung (Private Branch Exchange) für die Anrufweiterleitung verfügen.

## <a name="move-users-to-another-pool"></a>Verschieben von Benutzern in einen anderen Pool

Sie können Skype for Business Server Systemsteuerung verwenden, um Benutzern einen bestimmten Server oder Pool zuzuweisen.
 
> [!TIP]
> Das Verschieben aller vorhandenen Benutzer aus einem Quellpool, in dem Lync Server 2010 oder früher ausgeführt wird, in einen Skype for Business Server Zielpool in einer komplexen Active Directory-Umgebung kann zu einer langsameren Active Directory-Replikation führen. Um dies zu vermeiden, können Sie Suchfilter verwenden, um Benutzer aus Pools zu verschieben, die Lync Server 2010 oder früher separat ausführen, oder Sie können Skype for Business Server Verwaltungsshell verwenden, um Benutzer mit Cmdlets zu verschieben. Außerdem funktioniert die Filterfunktionalität mit Skype for Business Server Benutzern. 
 
### <a name="move-selected-users-to-a-different-server-or-pool-using-new-control-panel"></a>Verschieben ausgewählter Benutzer auf einen anderen Server oder Pool mithilfe der neuen Systemsteuerung

1. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.
 
2. Melden Sie sich mit einem Benutzerkonto an, das der Rolle "CsUserAdministrator" oder der Rolle "CsAdministrator" zugewiesen ist. 
 
3. Wählen Sie im linken Bereich **Benutzer** aus.
 
4. Geben Sie im **Suchfeld** den gesamten oder den ersten Teil des Anzeigenamens ein, und klicken Sie auf **"Suchen".**
 
5. Doppelklicken Sie in der Tabelle, um einen bestimmten Benutzer in der Liste auszuwählen. 

6. Klicken Sie im angezeigten Bereich auf das Stiftsymbol neben dem **Registrierungsstellenpool.**
 
7. Wählen Sie in **"Benutzer verschieben"** in der Dropdownliste den Pool aus, in den Sie die Benutzer verschieben möchten.
 
8. (Optional) Wenn der Zielserver oder -pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **"Erzwingen".**
 
    > [!CAUTION]
    > Wenn Sie **Erzwingen** aktivieren, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten werden gelöscht (z. B. von diesem Benutzer geplante Konferenzen). Wenn Sie diese Option nicht aktivieren, werden sowohl das Benutzerkonto als auch die zugehörigen Daten verschoben. 

> [!NOTE]
> Die neue Systemsteuerung ist für Skype for Business Server 2015 nicht verfügbar.

### <a name="move-selected-users-to-a-different-server-or-pool-using-legacy-control-panel"></a>Verschieben ausgewählter Benutzer auf einen anderen Server oder Pool mithilfe der älteren Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
 
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
 
3. Wählen Sie im linken Bereich **Benutzer** aus.
 
4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **Suchen**. 
 
5. Wählen Sie in der Tabelle einen bestimmten Benutzer oder benutzer in der Liste aus. 
 
6. Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben**.
 
7. Wählen Sie unter **"Benutzer verschieben"** den Pool aus, in den Sie die Benutzer im **Zielregistrierungsstellenpool** verschieben möchten.
 
8. (Optional) Wenn der Zielserver oder -pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **"Erzwingen".**
 
    > [!CAUTION]
    > Wenn Sie **Erzwingen** aktivieren, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten werden gelöscht (z. B. von diesem Benutzer geplante Konferenzen). Wenn Sie diese Option nicht aktivieren, werden sowohl das Benutzerkonto als auch die zugehörigen Daten verschoben. 
 
### <a name="move-users-from-one-pool-to-a-different-pool-by-using-a-filter-using-legacy-control-panel"></a>Verschieben von Benutzern aus einem Pool in einen anderen Pool mithilfe eines Filters mithilfe der älteren Systemsteuerung 

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
 
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
 
3. Wählen Sie im linken Bereich **Benutzer** aus.
 
4. Wählen Sie in **der Benutzersuche** die Option **"Suchen"** aus, und klicken Sie dann auf **"Filter hinzufügen".**
 
5. Wählen Sie in den Suchkriterien **Registrierungspool**, **Gleich** und **FQDN des aktuellen Pools** aus, und klicken Sie auf **Suchen**.
 
6. Wählen Sie im Menü **"Aktion"** die Option **"Alle Benutzer in Pool verschieben"** aus.
 
    > [!NOTE]
    > Wenn ein Filter auf eine vorhandene Gruppe von Benutzern angewendet wird, befindet sich die Option "Alle Benutzer in **Pool verschieben"** im Kontext der gefilterten Teilmenge der Benutzer, nicht **aller** möglichen Benutzer.
 
7. Wählen Sie im Abschnitt **Benutzer verschieben** unter **Quellregistrierungspool** den Pool aus, der die zu verschiebenden Benutzerkonten enthält.
 
8. Wählen Sie im **Zielregistrierungsstellenpool** den Pool aus, in den Sie die Benutzer verschieben möchten.
 
9. (Optional) Wenn der Zielserver oder -pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **"Erzwingen".**
 
    > [!CAUTION]
    > Wenn Sie **Erzwingen** aktivieren, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten werden gelöscht (z. B. Kontakte oder von diesem Benutzer geplante Konferenzen). Wenn Sie diese Option nicht aktivieren, werden sowohl das Benutzerkonto als auch die zugehörigen Daten verschoben. 
 
### <a name="move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Verschieben von Benutzern von einem Pool in einen anderen mithilfe Windows PowerShell Cmdlets

1. Je nachdem, wie Sie Windows PowerShell Befehle (lokal oder remote) ausführen, müssen Sie sich wie folgt als Mitglied der richtigen Skype for Business Server Administrativen Rollen anmelden:
 
    1. Wenn Sie die Befehle auf dem lokalen Computer ausführen (z. B. melden Sie sich direkt bei einem Front-End-Server an): Melden Sie sich bei dem Computer an, auf dem Skype for Business Server Verwaltungsshell als Mitglied der Gruppe "RTCUniversalServerAdmins" installiert ist, oder mit den erforderlichen Benutzerrechten, wie unter **Delegate Setup Permissions** beschrieben.
 
    2. Wenn Sie die Befehle remote auf einem anderen Computer ausführen (z. B. melden Sie sich bei Ihrem Computer an, und führen Sie die Befehle remote auf einem Standard Edition Front-End-Server aus): Melden Sie sich über ein Benutzerkonto, das der Rolle "CsUserAdministrator" oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.
 
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business** und dann auf **Skype for Business Server Verwaltungsshell.**
 
3. Zum Verschieben einzelner Benutzer verwenden Sie das Move-CsUser-Cmdlet wie folgt:
 
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    Der Zu verschiebende Benutzer ist der Benutzer Pilar Ackerman, und der Benutzer wird aus dem derzeit zugewiesenen Startpool in den Pool verschoben, pool01.contoso.net
 
4. Zum Verschieben einer großen Zahl von Benutzern verwenden Sie das **Get-CsUser**-Cmdlet mit Filtern und übergeben Sie den daraus resultierenden Benutzersatz an **Move-CsUser**:
 
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    Zusammen können die Befehle **Get-CsUser** und **Move-CsUser** Folgendes ergeben:
 
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```



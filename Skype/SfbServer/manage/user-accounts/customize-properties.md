---
title: Anpassen der Eigenschaften von Benutzerkonten für Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Die Verfahren können in diesem Abschnitt Sie einzelne Benutzerkontoeigenschaften ändern.
ms.openlocfilehash: 5162cb187538b5288f13f25beae96f3775faa594
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214835"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>Anpassen der Eigenschaften von Benutzerkonten für Skype für Business Server
 
Die Verfahren können in diesem Abschnitt Sie einzelne Benutzerkontoeigenschaften ändern.
  
Es gibt zwei grundlegende Vorgänge, die Ebene der einzelnen Benutzer ausgeführt werden können:
  
- [Konfigurieren von Telefonieoptionen für ein bestimmtes Benutzerkonto](customize-properties.md#Tel_Op)
    
- [Verschieben von Benutzern in einen anderen pool](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Konfigurieren von Telefonieoptionen für ein bestimmtes Benutzerkonto
<a name="Tel_Op"> </a>

Sie können die telefonieeinstellungen für einen bestimmten Benutzer (sofern der einzelne Benutzer für Skype für Business Server aktiviert wurde, und das Unternehmen Telefonie unterstützt) anpassen.
  
Skype für Business Server Benutzer Telefonieoptionen umfassen Folgendes:
  
- **Audio/Video deaktiviert.** Der Benutzer kann keine Anrufe mit audio und video tätigen.
    
- **PC-zu-PC nur** Der Benutzer kann nur PC-zu-PC-audio oder video Anrufe tätigen.
    
- **Enterprise-VoIP** Der Benutzer kann die Skype für Business Server-Infrastruktur verwenden, alle ein- und ausgehenden Anrufe weitergeleitet. Der Benutzer kann auch Anrufe von PC zu PC tätigen.
    
- **Remoteanrufsteuerung** Der Benutzer kann Skype für Business Server verwenden, um das herkömmliche Telefon steuern und kann auch Anrufe von PC zu PC tätigen.
    
Ausführliche Informationen zum Konfigurieren der Telefonie für eine Organisation finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in Skype für Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) und [Bereitstellen von Enterprise-VoIP in Skype für Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in der Bereitstellungsdokumentation.
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Suchen Benutzer** alle den ersten Teil der Anzeigename, Vorname, letzte Name, Kontonamen Sicherheitskontenverwaltung (SAM), SIP-Adresse oder Zeile URI Uniform Resource Identifier () für das Benutzerkonto an, dass Sie möchten, und klicken Sie dann auf **Suchen **.
    
5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie ändern möchten.
    
6. Klicken Sie im Menü **Bearbeiten** auf **Ändern**.
    
7. Folgendermaßen Sie in der **Telefonie**vor:
    
   - Um audio und video-Anrufe für den Benutzer zu deaktivieren, klicken Sie auf **Audio/Video deaktiviert**.
    
   - Um PC-zu-PC-audio-Kommunikation für den Benutzer, aber nicht die Remoteanrufsteuerung oder Enterprise-VoIP zu ermöglichen, klicken Sie auf **PC-zu-PC nur**. Geben Sie einen Wert für den **Anschluss-URI** für das Telefon, das der Benutzer für die PC-zu-PC-audio-Kommunikation verwendet.
    
   - Klicken Sie auf **Enterprise-VoIP**, so, dass der Benutzer Anrufe mithilfe der Skype für Business-Infrastruktur gemäß der Klasse des Service-Richtlinien, einschließlich Audiokommunikation PC zu PC weitergeleitet. Geben Sie im **Anschluss-URI**der Telefonnummer für Enterprise-VoIP. Geben Sie in der **Richtlinie für Wähleinstellungen** und **VoIP-Richtlinie**die entsprechenden Richtlinien für den Benutzer. Um die Normalisierungsregeln für die Übersetzung von Telefonnummern, die vom Benutzer in das e. 164-Format gewählt anzugeben, wählen Sie das entsprechende Standortprofil in **Standortrichtlinie**.
    
   - Zum Aktivieren der Remoteanrufsteuerung-Steuerelement, das Benutzer ihre Telefonen über Skype für Business Server so tätigen Anrufe von PC zu PC und Anrufe von Computer zu Telefon steuern kann, klicken Sie auf **die Remoteanrufsteuerung**. Geben Sie im **Anschluss-URI**die Telefonnummer für die Remoteanrufsteuerung. Der Benutzer benötigen ein herkömmliches Telefon und private Branch Exchange, (Nebenstellenanlage PBX) Verbindung zum Weiterleiten von Anrufen.
    
## <a name="move-users-to-another-pool"></a>Verschieben von Benutzern in einen anderen pool
<a name="Move_Users"> </a>

Skype für Business Server-Systemsteuerung können Sie Benutzer zu einem bestimmten Server oder Pool zuzuordnen.
  
> [!TIP]
> Verschieben alle vorhandenen Benutzer von einer Quellpool, die Lync Server 2010 ausgeführt wird oder früher in einer Skype für Business Server Zielpool in einer komplexen Active Directory-Umgebung möglicherweise langsamer Active Directory-Replikation. Um dies zu vermeiden, können Sie Suchfilter verwenden, um Benutzer von Pools zu verschieben, auf denen Lync Server 2010 ausgeführt werden oder zuvor getrennt, oder Sie können Skype für Business Server-Verwaltungsshell verwenden, um Benutzer mit Cmdlets zu verschieben. Darüber hinaus lässt sich die Funktionalität Filter mit Skype für Business Server-Benutzer. 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>So verschieben Sie ausgewählte Benutzer zu einem anderen Server oder pool

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Suchen Benutzer** alle den ersten Teil der Anzeigename, Vorname, letzte Name, Kontonamen Sicherheitskontenverwaltung (SAM), SIP-Adresse oder Zeile URI Uniform Resource Identifier () für das Benutzerkonto an, dass Sie möchten, und klicken Sie dann auf **Suchen **. 
    
5. Wählen Sie in der Tabelle einen bestimmten Benutzer oder Benutzer in der Liste aus. 
    
6. Klicken Sie im Menü **Aktion** auf **ausgewählte Benutzer in Pool verschieben**.
    
7. Wählen Sie den Pool, den Sie die Benutzer in **zielregistrierungsstellenpool**verschieben möchten, im Menü **Benutzer verschieben**.
    
8. (Optional) Wenn der Zielserver oder-Pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **erzwingen** .
    
    > [!CAUTION]
    > Wenn Sie **erzwingen**ausgewählt haben, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten (beispielsweise Konferenzen, die der Benutzer geplant wurde) gelöscht werden. Wenn Sie nicht ausgewählt, werden das Konto und die zugehörigen Daten verschoben. 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>So verschieben Sie alle Benutzer von einem Server oder Pool zu einem anderen Server oder pool

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Klicken Sie im Menü **Aktion** auf **alle Benutzer in Pool verschieben**.
    
5. **Benutzer verschieben**unter Wählen Sie den Pool mit den Benutzerkonten, die Sie in der **Quelle Registrar-Pool**verschieben möchten.
    
6. Wählen Sie im **zielregistrierungspool**den Pool, dem Sie die Benutzer verschieben möchten.
    
7. (Optional) Wenn der Zielserver oder-Pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **erzwingen** .
    
    > [!CAUTION]
    > Wenn Sie **erzwingen**ausgewählt haben, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten (beispielsweise Konferenzen, die der Benutzer geplant wurde) gelöscht werden. Wenn Sie nicht ausgewählt, werden das Konto und die zugehörigen Daten verschoben. 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>So verschieben Sie Benutzer aus einem Pool in einen anderen Pool mithilfe eines Filters

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Klicken Sie bei der **Suche für Benutzer**auf **Suchen**, und klicken Sie dann auf **Filter hinzufügen**.
    
5. Wählen Sie in den Suchkriterien **Registrar-Pool aus**, wählen Sie **gleich**, **FQDN des aktuellen Pools**aus, und klicken Sie dann auf **Suchen**.
    
6. Klicken Sie im Menü **Aktion** auf **alle Benutzer in Pool verschieben**.
    
    > [!NOTE]
    > Wenn ein Filter auf einen vorhandenen Satz von Benutzern, die Option angewendet wird, im Zusammenhang mit der gefilterten Teilmenge der Benutzer, die nicht **Alle** möglichen Benutzer **alle Benutzer in Pool verschieben ist** .
  
7. **Benutzer verschieben**unter Wählen Sie den Pool mit den Benutzerkonten, die Sie in der **Quelle Registrar-Pool**verschieben möchten.
    
8. Wählen Sie im **zielregistrierungspool**den Pool, in dem Sie die Benutzer verschieben möchten.
    
9. (Optional) Wenn der Zielserver oder-Pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **erzwingen** .
    
    > [!CAUTION]
    > Wenn Sie **erzwingen**auswählen, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten (z. B., Konferenzen, die der Benutzer geplant wurde und Kontakte) gelöscht werden. Wenn Sie nicht ausgewählt, werden das Konto und die zugehörigen Daten verschoben. 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>So verschieben Sie Benutzer aus einem Pool in einen anderen mithilfe von Windows Powershell-Cmdlets

1. Je nachdem, wie Sie Windows PowerShell-Befehle (d. h., lokal oder Remote) ausgeführt haben müssen Sie sich als Mitglied der richtigen Skype für Administratorrollen Business Server wie folgt auf:
    
   a. Wenn Sie die Befehle auf dem lokalen Computer (beispielsweise beim Anmelden direkt auf einem Front-End-Server) ausgeführt werden: Melden Sie sich an dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen installiert ist, Benutzerrechte, wie beschrieben unter **Delegate Setup Permissions**.
    
   b. Wenn Sie die Befehle Remote auf einem anderen Computer ausführen (z. B. Sie melden Sie sich an Ihren Computer und die Befehle Remote auf einem Standard Edition-Front-End-Server ausführen): von einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder die "csadministrator" zugewiesen ist, Rolle, melden Sie sich an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Unternehmen**und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.
    
3. Verwenden Sie das Cmdlet Move-CsUser zum Verschieben einzelner Benutzer wie folgt:
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    In dem der Benutzer zum Verschieben der Benutzer Pilar Ackerman, und der Benutzer ist wird aus ihrer derzeit zugeordneten Homepool in den Pool pool01.contoso.net verschoben werden
    
4. Um eine große Anzahl von Benutzern zu verschieben, Filter mit dem **Get-CsUser** -Cmdlet verwenden, und der Benutzer den daraus resultierenden Benutzersatz an **Move-CsUser**übergeben:
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    Zusammen können die Befehle **Get-CsUser** und **Move-CsUser** ergeben Folgendes:
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```



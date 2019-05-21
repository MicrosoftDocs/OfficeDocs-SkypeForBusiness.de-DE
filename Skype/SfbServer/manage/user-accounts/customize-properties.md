---
title: Anpassen der Eigenschaften des Benutzerkontos für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Mit den Verfahren in diesem Abschnitt können Sie einzelne Benutzerkontoeigenschaften ändern.
ms.openlocfilehash: d0e1a3ac02f5696e91e07c0f08cf0cf10e09f98e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275073"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>Anpassen der Eigenschaften des Benutzerkontos für Skype for Business Server
 
Mit den Verfahren in diesem Abschnitt können Sie einzelne Benutzerkontoeigenschaften ändern.
  
Es gibt zwei grundlegende Vorgänge, die auf der einzelnen Benutzerebene ausgeführt werden können:
  
- [Konfigurieren von Telefonoptionen für ein bestimmtes Benutzerkonto](customize-properties.md#Tel_Op)
    
- [Verschieben von Benutzern in einen anderen Pool](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Konfigurieren von Telefonoptionen für ein bestimmtes Benutzerkonto
<a name="Tel_Op"> </a>

Sie können die Telefoneinstellungen für einen bestimmten Benutzer anpassen (sofern der einzelne Benutzer für Skype for Business Server aktiviert wurde und die Organisation die Telefonie unterstützt).
  
Zu den Skype for Business Server-Optionen für Benutzer Telefonie gehören die folgenden:
  
- **Audio/Video deaktiviert** Der Benutzer kann mit Audio und Video keine Anrufe tätigen.
    
- **Nur PC-zu-PC** Der Benutzer kann nur PC-zu-PC-Audio-oder Videoanrufe tätigen.
    
- **Enterprise-VoIP** Der Benutzer kann mit der Skype for Business Server-Infrastruktur alle ein-und ausgehenden Anrufe weiterleiten. Der Benutzer kann auch PC-zu-PC-Anrufe tätigen.
    
- **Remote Anrufsteuerung** Der Benutzer kann Skype for Business Server verwenden, um das Desktoptelefon zu steuern, und kann auch PC-zu-PC-Anrufe tätigen.
    
Details zum Konfigurieren der Telefonie für eine Organisation finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) und [Bereitstellen von Enterprise-VoIP in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in der Bereitstellungsdokumentation.
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Benutzer suchen** den gesamten oder den ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontos (Security Accounts Manager), der SIP-Adresse oder des Uniform Resource Identifier (URI) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **suchen. **.
    
5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie ändern möchten.
    
6. Klicken Sie im Menü **Bearbeiten** auf **ändern**.
    
7. Führen Sie in **Telefonie**die folgenden Aktionen aus:
    
   - Wenn Sie Audio-und Videoanrufe für den Benutzer deaktivieren möchten, klicken Sie auf **Audio/Video deaktiviert**.
    
   - Wenn Sie die PC-zu-PC-Audiokommunikation für den Benutzer, aber nicht die Remoteanrufsteuerung oder Enterprise-VoIP aktivieren möchten, klicken Sie auf **nur PC-zu-** PC. Geben Sie einen Wert für den Leitungs- **URI** für das Telefon an, das der Benutzer für die PC-zu-PC-Audiokommunikation verwendet.
    
   - Klicken Sie auf **Enterprise-VoIP**, um die Telefonanrufe des Benutzers über die Skype for Business-Infrastruktur in Übereinstimmung mit der Service Richtlinienklasse zu leiten, einschließlich der PC-zu-PC-Audiokommunikation. Geben Sie in der **Zeile URI**die Telefonnummer für Enterprise-VoIP an. Geben Sie in der Richtlinie für **Wähl Plan Richtlinien** und **VoIP**die entsprechenden Richtlinien für den Benutzer an. Wenn Sie die Normalisierungsregeln für die Übersetzung von Telefonnummern angeben möchten, die vom Benutzer im E. 164-Format gewählt wurden, wählen Sie das entsprechende Standortprofil in der **ortungsrichtlinie**aus.
    
   - Klicken Sie auf **Remoteanrufsteuerung**, um die Remoteanrufsteuerung zu aktivieren, mit der Benutzer Ihre Desktop-Telefonleitung von Skype for Business Server steuern können, um PC-zu-PC-Anrufe zu tätigen und PC-zu-Telefon-Anrufe zu tätigen. Geben Sie in der **Zeile URI**die Telefonnummer für die Remoteanrufsteuerung ein. Der Benutzer muss über ein Desktoptelefon und eine PBX-Verbindung (Private Branch Exchange) für das Anrufrouting verfügen.
    
## <a name="move-users-to-another-pool"></a>Verschieben von Benutzern in einen anderen Pool
<a name="Move_Users"> </a>

Sie können die Skype for Business Server-Systemsteuerung verwenden, um Benutzer einem bestimmten Server oder Pool zuzuweisen.
  
> [!TIP]
> Das Verschieben aller vorhandenen Benutzer aus einem Quell Pool, auf dem lync Server 2010 oder früher ausgeführt wird, zu einem Skype for Business Server-Ziel Pool in einer komplexen Active Directory-Umgebung kann zu einer langsameren Active Directory-Replikation führen. Um dies zu vermeiden, können Sie mithilfe von Suchfiltern Benutzer aus Pools verschieben, auf denen lync Server 2010 oder früher separat ausgeführt wird, oder Sie können die Skype for Business Server-Verwaltungsshell verwenden, um Benutzer mit Cmdlets zu verschieben. Die Filterfunktionalität funktioniert auch mit Skype for Business Server-Benutzern. 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>So verschieben Sie ausgewählte Benutzer auf einen anderen Server oder Pool

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Benutzer suchen** den gesamten oder den ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontos (Security Accounts Manager), der SIP-Adresse oder des Uniform Resource Identifier (URI) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **suchen. **. 
    
5. Wählen Sie in der Tabelle einen bestimmten Benutzer oder Benutzer in der Liste aus. 
    
6. Klicken Sie im Menü **Aktion** auf **ausgewählte Benutzer in Pool verschieben**.
    
7. Wählen Sie in **Benutzer verschieben**den Pool aus, in den Sie die Benutzer in den **Ziel Registrierungspool**verschieben möchten.
    
8. Optional Aktivieren Sie das Kontrollkästchen **erzwingen** , wenn der Zielserver oder-Pool nicht verfügbar ist.
    
    > [!CAUTION]
    > Wenn Sie **erzwingen**auswählen, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten werden gelöscht (beispielsweise Konferenzen, die der Benutzer geplant hat). Wenn Sie diese Option nicht auswählen, werden sowohl das Konto als auch die zugehörigen Daten verschoben. 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>So verschieben Sie alle Benutzer von einem Server oder Pool auf einen anderen Server oder Pool

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Klicken Sie im Menü **Aktion** auf **alle Benutzer in Pool verschieben**.
    
5. Wählen Sie in **Benutzer verschieben**den Pool aus, der die Benutzerkonten enthält, die Sie im **Quell Registrierungspool**verschieben möchten.
    
6. Wählen Sie im **Ziel Registrierungspool**den Pool aus, in den Sie die Benutzer verschieben möchten.
    
7. Optional Aktivieren Sie das Kontrollkästchen **erzwingen** , wenn der Zielserver oder-Pool nicht verfügbar ist.
    
    > [!CAUTION]
    > Wenn Sie **erzwingen**auswählen, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten werden gelöscht (beispielsweise Konferenzen, die der Benutzer geplant hat). Wenn Sie diese Option nicht auswählen, werden sowohl das Konto als auch die zugehörigen Daten verschoben. 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>So verschieben Sie Benutzer mithilfe eines Filters aus einem Pool in einen anderen Pool

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Klicken Sie in der **Benutzersuche**auf **Suchen**, und klicken Sie dann auf **Filter hinzufügen**.
    
5. Wählen Sie in den Suchkriterien den Eintrag **Registrierungspool**aus, wählen Sie **gleich**aus, wählen Sie **Aktueller Pool-FQDN**aus, und klicken Sie dann auf **Suchen**.
    
6. Klicken Sie im Menü **Aktion** auf **alle Benutzer in Pool verschieben**.
    
    > [!NOTE]
    > Wenn ein Filter auf eine vorhandene Gruppe von Benutzern angewendet wird, befindet sich die Option **alle Benutzer in Pool verschieben** im Kontext der gefilterten Teilmenge von Benutzern, nicht **aller** möglichen Benutzer.
  
7. Wählen Sie in **Benutzer verschieben**den Pool aus, der die Benutzerkonten enthält, die Sie im **Quell Registrierungspool**verschieben möchten.
    
8. Wählen Sie im **Ziel Registrierungspool**den Pool aus, in den Sie die Benutzer verschieben möchten.
    
9. Optional Aktivieren Sie das Kontrollkästchen **erzwingen** , wenn der Zielserver oder-Pool nicht verfügbar ist.
    
    > [!CAUTION]
    > Wenn Sie **erzwingen**auswählen, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten werden gelöscht (beispielsweise Konferenzen, die der Benutzer geplant hat, und Kontakte). Wenn Sie diese Option nicht auswählen, werden sowohl das Konto als auch die zugehörigen Daten verschoben. 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>So verschieben Sie Benutzer mithilfe von Windows PowerShell-Cmdlets aus einem Pool in einen anderen

1. Je nachdem, wie Sie Windows PowerShell-Befehle ausführen (lokal oder Remote), müssen Sie sich wie folgt als Mitglied der richtigen Skype for Business Server-Administratorrolle anmelden:
    
   a. Wenn Sie die Befehle auf dem lokalen Computer ausführen (beispielsweise melden Sie sich direkt bei einem Front-End-Server an): Melden Sie sich bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe installiert ist, oder mit den erforderlichen Benutzerrechte wie unter Delegieren von **Setup Berechtigungen**beschrieben.
    
   b. Wenn Sie die Befehle Remote auf einem anderen Computer ausführen (beispielsweise melden Sie sich bei Ihrem Computer an, und führen Sie die Befehle Remote auf einem Standard Edition-Front-End-Server aus): von einem Benutzerkonto, das der CsUserAdministrator-Rolle oder dem CsAdministrator zugewiesen ist. Rolle, melden Sie sich bei einem beliebigen Computer in ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for**Business, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.
    
3. Verwenden Sie zum Verschieben einzelner Benutzer das Cmdlet Move-CsUser wie folgt:
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    Der Benutzer, der verschoben werden soll, ist der Benutzer Pilar Ackerman, und der Benutzer wird aus dem aktuell zugewiesenen privaten Pool in den Pool pool01.contoso.net
    
4. Wenn Sie eine große Anzahl von Benutzern verschieben möchten, verwenden Sie Filter mit dem Cmdlet **Get-CsUser** , und übergeben Sie die resultierenden Benutzersätze an **Move-CsUser**:
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    Die kombinierten Befehle von **Get-CsUser** und **Move-CsUser** können dazu führen:
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```



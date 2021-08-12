---
title: Bereitstellen von Netzwerkregionen, Standorten und Subnetzen in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 'Erstellen oder Ändern von Netzwerkregionen, Netzwerkstandorten und Zuordnen von Netzwerksubnetzen in Skype for Business Server. Alle diese Werden für die erweiterten Enterprise-VoIP Features verwendet: Medienumgehung, Anrufsteuerung und standortbasiertes Routing.'
ms.openlocfilehash: e031936fe8f8411f5527812326b751da59c2a05f77b7162a40901588bbc6138e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320887"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a>Bereitstellen von Netzwerkregionen, Standorten und Subnetzen in Skype for Business

Erstellen oder Ändern von Netzwerkregionen, Netzwerkstandorten und Zuordnen von Netzwerksubnetzen in Skype for Business Server. Alle diese Werden für die erweiterten Enterprise-VoIP Features verwendet: Medienumgehung, Anrufsteuerung und standortbasiertes Routing.

Die erweiterten Enterprise-VoIP Features sind [Anrufsteuerung,](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) [Medienumgehung,](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md) [standortbasiertes Routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)und [E9-1-1.](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md) Für diese Features müssen Sie Netzwerkregionen, Netzwerkstandorte und Subnetze erstellen. Für alle diese Features muss beispielsweise jedes Subnetz in Ihrer Topologie einem bestimmten Netzwerkstandort zugeordnet sein, und jeder Netzwerkstandort muss einer Netzwerkregion zugeordnet sein. Weitere Informationen zu diesen Bedingungen finden Sie unter ["Netzwerkeinstellungen" für die erweiterten Enterprise-VoIP-Features in Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)

Für die Anrufsteuerung und E9-1-1 gelten bei den Netzwerkstandorten zusätzliche Konfigurationsanforderungen:

- Die Anrufsteuerung erfordert, dass ein Bandbreitenrichtlinienprofil für jeden Standort angegeben wird, für den WAN-Bandbreiteneinschränkungen gelten. Wenn Sie die Anrufsteuerung bereitstellen möchten, müssen Sie [Bandbreitenrichtlinienprofile in Skype for Business Server erstellen,](create-bandwidth-policy-profiles.md) bevor Sie Ihre Netzwerkstandorte konfigurieren.

- Für E9-1-1 ist es erforderlich, dass für jeden Standort eine Standortrichtlinie angegeben ist. Wenn Sie beabsichtigen, E9-1-1 bereitzustellen, müssen Sie [Standortrichtlinien in Skype for Business Server erstellen,](create-location-policies.md) bevor Sie Ihre Netzwerkstandorte konfigurieren.

## <a name="create-or-modify-a-network-region"></a>Erstellen oder Ändern einer Netzwerkregion

Wenn Sie bereits Netzwerkregionen für eines dieser Features erstellt haben, müssen Sie keine neuen Netzwerkregionen erstellen. Andere erweiterte Enterprise-VoIP-Features verwenden dieselben Netzwerkregionen.

Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben.

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a>So erstellen Sie eine Netzwerkregion mit Skype for Business Server Verwaltungsshell

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**

2. Führen Sie das Cmdlet "New-CsNetworkRegion" aus, um Netzwerkregionen zu erstellen:

   ```powershell
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Beispiel:

   ```powershell
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    In diesem Beispiel haben Sie eine Netzwerkregion namens "NorthAmerica" erstellt, die einem zentralen Standort mit der Standort-ID CHICAGO zugeordnet ist.

3. Zum Abschließen der Erstellung von Netzwerkregionen für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Netzwerkregionen.

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a>So erstellen Sie eine Netzwerkregion mit Skype for Business Server Systemsteuerung

1. Öffnen Sie Skype for Business Server Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3. Klicken Sie auf **Region**.

4. Klicken Sie auf **Neu**.

5. Klicken Sie auf der Seite **Neue Region** auf **Name**, und geben Sie einen Namen für die Netzwerkregion ein.

6. Klicken Sie auf **Zentraler Standort** und anschließend auf einen zentralen Standort in der Liste.

7. Klicken Sie optional auf **Beschreibung**, und geben Sie zusätzliche Informationen zur Beschreibung dieses Netzwerkstandorts ein.

8. Klicken Sie auf **Commit ausführen**.

9. Zum Abschließen der Erstellung von Netzwerkregionen für Ihre Topologie wiederholen Sie die Schritte 4 bis 8 mit Einstellungen für weitere Regionen.

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a>So ändern Sie eine Netzwerkregion mit Skype for Business Server Verwaltungsshell

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**

2. Führen Sie das Cmdlet "Set-CsNetworkRegion" aus, um eine vorhandene Netzwerkregion zu ändern:

   ```powershell
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Beispiel:

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    In diesem Beispiel haben Sie eine vorhandene Netzwerkregion namens "NorthAmerica" (erstellt mit den verfahren weiter oben in diesem Thema) geändert, indem Sie die Beschreibung ändern. Wenn für die Region "NorthAmerica" eine Beschreibung vorhanden ist, überschreibt dieser Befehl sie mit diesem Wert. wenn keine Beschreibung festgelegt wurde, wird sie mit diesem Befehl festgelegt.

3. Zum Ändern weiterer Netzwerkregionen wiederholen Sie Schritt 2 mit Einstellungen für andere Regionen.

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a>So ändern Sie eine Netzwerkregion mit Skype for Business Server Systemsteuerung

1. Öffnen Sie Skype for Business Server Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3. Klicken Sie auf die Navigationsschaltfläche **Region**.

4. Klicken Sie in der Tabelle auf die Netzwerkregion, die Sie ändern möchten.

5. Klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.

6. Ändern Sie auf der Seite "Region **bearbeiten"** die Werte für die Einstellungen dieser Netzwerkregion entsprechend.

7. Klicken Sie auf **Commit ausführen**.

8. Zum Abschließen der Änderung von Netzwerkregionen wiederholen Sie die Schritte 4 bis 7 mit Einstellungen für weitere Regionen.

## <a name="create-or-modify-a-network-site"></a>Erstellen oder Ändern eines Netzwerkstandorts

Wenn Sie bereits Netzwerkstandorte für eines dieser Features erstellt haben, müssen Sie keine neuen Netzwerkstandorte erstellen. Andere erweiterte Enterprise-VoIP-Features verwenden dieselben Netzwerkstandorte. Sie müssen jedoch möglicherweise eine vorhandene Netzwerkstandortdefinition ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie beispielsweise einen Netzwerkstandort für E9-1-1 erstellt haben, müssen Sie den Netzwerkstandort während der Bereitstellung der Anrufsteuerung ändern, um ein Bandbreitenrichtlinienprofil anzuwenden.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a>So erstellen Sie einen Netzwerkstandort mithilfe Skype for Business Server Verwaltungsshell

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**

2. Führen Sie das Cmdlet "New-CsNetworkSite" aus, um Netzwerkstandorte zu erstellen:

   ```powershell
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    Beispiel:

   ```powershell
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    In diesem Beispiel haben Sie einen Netzwerkstandort namens "Chicago" erstellt, der sich in der Netzwerkregion "NorthAmerica" befindet.

    > [!NOTE]
    > Die Netzwerkregion "NorthAmerica" muss bereits vorhanden sein, damit dieser Befehl erfolgreich ausgeführt werden kann.

3. Zum Abschließen der Erstellung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a>So erstellen Sie einen Netzwerkstandort mithilfe Skype for Business Server Systemsteuerung

1. Öffnen Sie Skype for Business Server Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3. Klicken Sie auf die Navigationsschaltfläche **Standort**.

4. Klicken Sie auf **Neu**.

5. Klicken Sie auf der Seite **Neuer Standort** auf **Name**, und geben Sie einen Namen für den Netzwerkstandort ein.

6. Klicken Sie auf **Region**, und klicken Sie dann auf eine Region in der Liste.

7. Klicken Sie optional auf **Bandbreitenrichtlinie**, und klicken Sie dann auf eine Bandbreitenrichtlinie in der Liste.

    > [!NOTE]
    > Eine Bandbreitenrichtlinie ist nur dann erforderlich, wenn Sie die Anrufsteuerung am Standort bereitstellen möchten.

8. Klicken Sie optional auf **Ortungsrichtlinie**, und klicken Sie dann auf eine Ortungsrichtlinie in der Liste.

    > [!NOTE]
    > Eine Ortungsrichtlinie ist nur erforderlich, wenn Sie E9-1-1 am Standort bereitstellen.

9. Klicken Sie optional auf **Beschreibung**, und geben Sie zusätzliche Informationen zur Beschreibung dieses Netzwerkstandorts ein.

10. Klicken Sie auf **Commit**.

11. Zum Abschließen der Erstellung von Netzwerkstandorten für Ihre Topologie wiederholen Sie die Schritte 4 bis 10 mit Einstellungen für weitere Standorte.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a>So ändern Sie einen Netzwerkstandort mithilfe Skype for Business Server Verwaltungsshell

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**

2. Führen Sie das Cmdlet "Set-CsNetworkSite" aus, um Netzwerkstandorte zu ändern:

   ```powershell
   Set-CsNetworkSite -Identity <string>
   ```

    Beispiel:

   ```powershell
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    In diesem Beispiel wird der Standort "Albuquerque" in die Netzwerkregion "NorthAmerica" verschoben. Bearbeiten Sie zum Ändern der Netzwerkstandortkonfiguration für die Bereitstellung von Anrufsteuerung, E9-1-1 oder Medienumgehung die Netzwerkstandorteinstellungen, indem Sie das Cmdlet "Set-CsNetworkSite" mit dem Parameter "BWPolicyProfileID" oder "LocationPolicy" ausführen.

    > [!NOTE]
    > Wenngleich der Parameter "BypassID" für die Medienumgehung vorhanden ist, wird dringend empfohlen, automatisch generierte IDs für die Umgehung nicht außer Kraft zu setzen. Sie müssen keine zusätzlichen Parameter angeben, um einen Netzwerkstandort für die Medienumgehung zu konfigurieren.

3. Zum Abschließen der Änderung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a>So ändern Sie einen Netzwerkstandort mithilfe Skype for Business Server Systemsteuerung

1. Öffnen Sie Skype for Business Server Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3. Klicken Sie auf die Navigationsschaltfläche **Standort**.

4. Klicken Sie in der Tabelle auf den Netzwerkstandort, den Sie ändern möchten.

5. Klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.

6. Ändern Sie auf der Seite **"Website bearbeiten"** die Werte für die Einstellungen dieses Netzwerkstandorts nach Bedarf.

7. Klicken Sie auf **Commit**.

8. Zum Abschließen der Änderung von Netzwerkstandorten wiederholen Sie die Schritte 4 bis 7 mit Einstellungen für weitere Standorte.

## <a name="associate-a-subnet-with-a-network-site"></a>Zuordnen eines Subnetzes zu einem Netzwerkstandort
<a name="BKMK_AssociateSubnets"> </a>

Jedes Subnetz in Ihrem Netzwerk muss einem bestimmten Netzwerkstandort zugeordnet sein, da mithilfe von Subnetzinformationen der Netzwerkstandort ermittelt wird, an dem sich ein Endpunkt befindet, während eine neuen Sitzung initiiert wird. Wenn der Standort der einzelnen Teilnehmer in einer Sitzung bekannt ist, können erweiterte Enterprise-VoIP Features diese Informationen anwenden, um zu bestimmen, wie die Anrufeinrichtung oder das Routing behandelt werden soll.

Alle konfigurierten öffentlichen IP-Adressen der Audio-Video-Edgeserver in Ihrer Bereitstellung müssen den Netzwerkkonfigurationseinstellungen hinzugefügt werden. Diese IP-Adressen werden als Subnetze mit der Maske 32 hinzugefügt. Der zugeordnete Netzwerkstandort muss dem jeweiligen konfigurierten Netzwerkstandort entsprechen. Die öffentliche IP-Adresse, die dem A/V-Edgedienst am zentralen Standort Chicago entspricht, lautet beispielsweise NetworkSiteID Chicago.

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a>So ordnen Sie ein Subnetz mithilfe Skype for Business Server Verwaltungsshell einem Netzwerkstandort zu

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**

2. Führen Sie das Cmdlet **New-CsNetworkSubnet** aus, um ein Subnetz einem Netzwerkstandort zuzuordnen:

   ```powershell
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    Zum Beispiel:

   ```powershell
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    In diesem Beispiel haben Sie eine Zuordnung zwischen dem Subnetz 172.11.12.13 und dem Netzwerkstandort "Chicago" erstellt.

3. Wiederholen Sie Schritt 2 für alle Subnetze in der Topologie.

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>So ordnen Sie Subnetze durch Importieren einer CSV-Datei Netzwerkstandorten zu

1. Erstellen Sie eine CSV-Datei, die alle Subnetze enthält, die Sie hinzufügen möchten. Erstellen Sie beispielsweise die Datei **Subnetz.csv** mit folgendem Inhalt:

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**

3. Führen Sie das folgende Cmdlet aus, um **subnet.csv** zu importieren und dann den Inhalt im Lync Server-Verwaltungsspeicher zu speichern:

   ```powershell
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a>So ordnen Sie ein Subnetz mithilfe Skype for Business Server Systemsteuerung einem Netzwerkstandort zu

1. Öffnen Sie Skype for Business Server Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3. Klicken Sie auf die Navigationsschaltfläche **Subnetz**.

4. Klicken Sie auf **Neu**.

5. Klicken Sie auf der Seite **Neues Subnetz** auf **Subnetz-ID**, und geben Sie dann die erste Adresse in den IP-Adressbereich ein, der von dem Subnetz definiert wird, das Sie einem Netzwerkstandort zuordnen möchten.

6. Klicken Sie auf **Maske**, und geben Sie die Bitmaske für das Subnetz ein.

7. Klicken Sie auf **Netzwerkstandort-ID**, und wählen Sie die Standort-ID des Standorts aus, dem Sie dieses Subnetz hinzufügen.

    > [!NOTE]
    > Wenn Sie noch keine Netzwerkstandorte erstellt haben, ist diese Liste leer. Ausführliche Informationen zu dem Verfahren finden Sie unter [Create or Modify a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site). Sie können auch Standort-IDs für Ihre Bereitstellung abrufen, indem Sie das Cmdlet **Get-CsNetworkSite** ausführen. Ausführliche Informationen finden Sie in der Dokumentation zur Skype for Business Server Verwaltungsshell.

8. Klicken Sie optional auf **Beschreibung**, und geben Sie zusätzliche Informationen zur Beschreibung dieses Subnetzes ein.

9. Klicken Sie auf **Commit**.

Wiederholen Sie diese Schritte, um einem Netzwerkstandort weitere Subnetze hinzuzufügen.
> [!NOTE]
> Es wird eine KHI-Warnung (Key Health Indicator) ausgelöst, die eine Liste der IP-Adressen angibt, die in Ihrem Netzwerk vorhanden sind, aber entweder keinem Subnetz zugeordnet sind, oder das Subnetz, das die IP-Adressen enthält, ist keinem Netzwerkstandort zugeordnet. Diese Warnung wird innerhalb eines Zeitraums von 8 Stunden nicht mehrmals ausgelöst.

Die relevanten Warnungsinformationen und ein Beispiel sind wie folgt:

 **Quelle**: CS-Bandbreitenrichtliniendienst (Core)

 **Ereignisnummer**: 36034

 **Ebene**: 2

 **Beschreibung:** Die Subnetze für die folgenden IP-Adressen: \<List of IP Addresses\> sind entweder nicht konfiguriert oder die Subnetze sind keinem Netzwerkstandort zugeordnet.

 **Ursache**: Die Subnetze für die zugehörigen IP-Adressen fehlen in den Netzwerkkonfigurationseinstellungen, oder die Subnetze sind keinem Netzwerkstandort zugeordnet.

 **Lösung**: Fügen Sie gemäß der IP-Adressenliste den Netzwerkkonfigurationseinstellungen Subnetze hinzu, und ordnen Sie jedes Subnetz einem Netzwerkstandort zu.

Wenn die Liste der IP-Adressen beispielsweise die Einträge 10.121.248.226 und 10.121.249.20 enthält, sind diese IP-Adressen entweder keinem Subnetz zugeordnet, oder das zugeordnete Subnetz gehört keinem Netzwerkstandort an. Wenn die zugehörigen Subnetze für diese Adressen 10.121.248.0/24 und 10.121.249.0/24 lauten, können Sie das Problem wie folgt lösen:

1. Stellen Sie sicher, dass die IP-Adresse 10.121.248.226 dem Subnetz 10.121.248.0/24 und die IP-Adresse 10.121.249.20 dem Subnetz 10.121.249.0/24 zugeordnet ist.

2. Stellen Sie sicher, dass die Subnetze 10.121.248.0/24 und 10.121.249.0/24 jeweils einem Netzwerkstandort zugeordnet sind.

## <a name="see-also"></a>Siehe auch
<a name="BKMK_AssociateSubnets"> </a>


[New-CsNetworkRegion](/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[Set-CsNetworkRegion](/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[Remove-CsNetworkRegion](/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)
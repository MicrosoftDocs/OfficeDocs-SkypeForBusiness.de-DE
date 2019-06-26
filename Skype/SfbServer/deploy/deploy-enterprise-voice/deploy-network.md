---
title: Bereitstellen von netzwerkregionen,-Websites und-Subnetzen in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 'Sie können netzwerkregionen, Netzwerk Websites und Netzwerk-Subnetze in Skype for Business Server erstellen oder ändern. Alle diese Funktionen werden für die erweiterten Enterprise-VoIP-Features verwendet: medienumgehung, Anrufsteuerung und standortbasiertes Routing.'
ms.openlocfilehash: 3ce0f4dcf011f57e25c4741c34135bc4ba62085a
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221483"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a>Bereitstellen von netzwerkregionen,-Websites und-Subnetzen in Skype for Business

Sie können netzwerkregionen, Netzwerk Websites und Netzwerk-Subnetze in Skype for Business Server erstellen oder ändern. Alle diese Funktionen werden für die erweiterten Enterprise-VoIP-Features verwendet: medienumgehung, Anrufsteuerung und standortbasiertes Routing.

Zu den erweiterten Enterprise-VoIP-Features gehören [Anrufsteuerung](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [medienumgehung](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [Orts basiertes Routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)und [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md). Für alle diese Funktionen müssen Sie Netzwerkregionen, Netzwerkstandorte und Subnetze erstellen. Beispiel: Für alle diese Funktionen ist es erforderlich, dass jedes Subnetz in Ihrer Topologie einem bestimmten Netzwerkstandort und jeder Netzwerkstandort einer Netzwerkregion zugeordnet ist. Weitere Informationen zu diesen Begriffen finden Sie unter [Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md).

Für die Anrufsteuerung und E9-1-1 gelten bei den Netzwerkstandorten zusätzliche Konfigurationsanforderungen:

- Die Anrufsteuerung erfordert, dass ein Bandbreitenrichtlinienprofil für jeden Standort angegeben wird, für den WAN-Bandbreiteneinschränkungen gelten. Wenn Sie beabsichtigen, die Anrufsteuerung bereitzustellen, müssen Sie [in Skype for Business Server bandbreitenrichtlinienprofile erstellen](create-bandwidth-policy-profiles.md) , bevor Sie Ihre Netzwerk Websites konfigurieren.

- Für E9-1-1 ist es erforderlich, dass für jeden Standort eine Standortrichtlinie angegeben ist. Wenn Sie die Bereitstellung von E9-1-1 planen, müssen Sie [in Skype for Business Server Standortrichtlinien erstellen](create-location-policies.md) , bevor Sie Ihre Netzwerk Websites konfigurieren.

## <a name="create-or-modify-a-network-region"></a>Erstellen oder Ändern einer Netzwerkregion

Wenn Sie bereits netzwerkregionen für eines dieser Funktionen erstellt haben, müssen Sie keine neuen netzwerkregionen erstellen. für andere erweiterte Enterprise-VoIP-Features werden dieselben netzwerkregionen verwendet.

Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben.

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a>So erstellen Sie einen Netzwerkbereich mit der Skype for Business Server-Verwaltungsshell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

2. Führen Sie das Cmdlet New-CsNetworkRegion aus, um Netzwerkregionen zu erstellen:

   ```
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Beispiel:

   ```
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    In diesem Beispiel haben Sie einen Netzwerkbereich mit dem Namen "Northamerica" erstellt, der einem zentralen Standort mit der Website-ID Chicago zugeordnet ist.

3. Zum Abschließen der Erstellung von Netzwerkregionen für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Netzwerkregionen.

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a>So erstellen Sie einen Netzwerkbereich mit der Skype for Business Server-Systemsteuerung

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3. Klicken Sie auf **Region**.

4. Klicken Sie auf **Neu**.

5. Klicken Sie auf der Seite **Neue Region** auf **Name** und geben Sie einen Namen für die Netzwerkregion ein.

6. Klicken Sie auf **Zentraler Standort** und anschließend auf einen zentralen Standort in der Liste.

7. Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Netzwerkstandorts ein.

8. Klicken Sie auf **Commit ausführen**.

9. Zum Abschließen der Erstellung von Netzwerkregionen für Ihre Topologie wiederholen Sie die Schritte 4 bis 8 mit Einstellungen für weitere Regionen.

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a>So ändern Sie einen Netzwerkbereich mit der Skype for Business Server-Verwaltungsshell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

2. Führen Sie das Cmdlet Set-CsNetworkRegion aus, um eine vorhandene Netzwerkregion zu ändern:

   ```
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Beispiel:

   ```
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    In diesem Beispiel haben Sie eine vorhandene netzwerkregion mit dem Namen "Northamerica" (erstellt mit den Verfahren weiter oben in diesem Thema) geändert, indem Sie die Beschreibung geändert haben. Wenn für den Bereich "Northamerica" eine Beschreibung vorhanden ist, wird dieser durch diesen Befehl mit diesem Wert überschrieben. Wenn keine Beschreibung festgelegt wurde, wird Sie durch diesen Befehl festgelegt.

3. Zum Ändern weiterer Netzwerkregionen wiederholen Sie Schritt 2 mit Einstellungen für andere Regionen.

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a>So ändern Sie einen Netzwerkbereich mit der Skype for Business Server-Systemsteuerung

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3. Klicken Sie auf die Navigationsschaltfläche **Region**.

4. Klicken Sie in der Tabelle auf die Netzwerkregion, die Sie ändern möchten.

5. Klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.

6. Ändern Sie auf der Seite " **Bereich bearbeiten** " die Werte für die Einstellungen dieses Netzwerkbereichs entsprechend.

7. Klicken Sie auf **Commit ausführen**.

8. Zum Abschließen der Änderung von Netzwerkregionen wiederholen Sie die Schritte 4 bis 7 mit Einstellungen für weitere Regionen.

## <a name="create-or-modify-a-network-site"></a>Erstellen oder Ändern eines Netzwerkstandorts

Wenn Sie bereits Netzwerk Websites für eines dieser Funktionen erstellt haben, müssen Sie keine neuen Netzwerk Websites erstellen. für andere erweiterte Enterprise-VoIP-Features werden dieselben Netzwerk Websites verwendet. Sie müssen jedoch möglicherweise eine vorhandene Definition eines Netzwerkstandorts ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. einen Netzwerkstandort für E9-1-1 erstellt haben, müssen Sie den Netzwerkstandort während der Bereitstellung der Anrufsteuerung ändern, um ein Bandbreitenrichtlinienprofil anzuwenden.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a>So erstellen Sie eine Netzwerk Website mithilfe der Skype for Business Server-Verwaltungsshell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

2. Führen Sie das Cmdlet New-CsNetworkSite aus, um Netzwerkstandorte zu erstellen:

   ```
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    Beispiel:

   ```
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    In diesem Beispiel haben Sie eine Netzwerk Website mit dem Namen "Chicago" erstellt, die sich in der netzwerkregion "Northamerica" befindet.

    > [!NOTE]
    > Die Netzwerkregion „NorthAmerica“ muss bereits vorhanden sein, damit dieser Befehl erfolgreich ausgeführt werden kann.

3. Zum Abschließen der Erstellung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a>So erstellen Sie eine Netzwerk Website mithilfe der Skype for Business Server-Systemsteuerung

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3. Klicken Sie auf die Navigationsschaltfläche **Standort**.

4. Klicken Sie auf **Neu**.

5. Klicken Sie auf der Seite **Neuer Standort** auf **Name** und geben Sie einen Namen für den Netzwerkstandort ein.

6. Klicken Sie auf **Region** und klicken Sie dann auf eine Region in der Liste.

7. Klicken Sie optional auf **Bandbreitenrichtlinie** und klicken Sie dann auf eine Bandbreitenrichtlinie in der Liste.

    > [!NOTE]
    > Eine Bandbreitenrichtlinie ist nur dann erforderlich, wenn Sie die Anrufsteuerung am Standort bereitstellen möchten.

8. Klicken Sie optional auf **Ortungsrichtlinie** und klicken Sie dann auf eine Ortungsrichtlinie in der Liste.

    > [!NOTE]
    > Eine Ortungsrichtlinie ist nur erforderlich, wenn Sie E9-1-1 am Standort bereitstellen.

9. Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Netzwerkstandorts ein.

10. Klicken Sie auf **Commit ausführen**.

11. Zum Abschließen der Erstellung von Netzwerkstandorten für Ihre Topologie wiederholen Sie die Schritte 4 bis 10 mit Einstellungen für weitere Standorte.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a>So ändern Sie eine Netzwerk Website mithilfe der Skype for Business Server-Verwaltungsshell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

2. Führen Sie das Cmdlet Set-CsNetworkSite aus, um Netzwerkstandorte zu ändern:

   ```
   Set-CsNetworkSite -Identity <string>
   ```

    Beispiel:

   ```
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    In diesem Beispiel wird die Website mit dem Namen "Albuquerque" in die netzwerkregion "Northamerica" verschoben. Bearbeiten Sie zum Ändern der Netzwerkstandortkonfiguration für die Bereitstellung von Anrufsteuerung, E9-1-1 oder Medienumgehung die Netzwerkstandorteinstellungen, indem Sie das Cmdlet Set-CsNetworkSite mit dem Parameter BWPolicyProfileID oder LocationPolicy ausführen.

    > [!NOTE]
    > Wenngleich der Parameter BypassID für die Medienumgehung vorhanden ist, wird dringend empfohlen, automatisch generierte IDs für die Umgehung nicht außer Kraft zu setzen. Sie müssen keine zusätzlichen Parameter angeben, um einen Netzwerkstandort für die Medienumgehung zu konfigurieren.

3. Zum Abschließen der Änderung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a>So ändern Sie eine Netzwerk Website mithilfe der Skype for Business Server-Systemsteuerung

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3. Klicken Sie auf die Navigationsschaltfläche **Standort**.

4. Klicken Sie in der Tabelle auf den Netzwerkstandort, den Sie ändern möchten.

5. Klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.

6. Ändern Sie auf der Seite " **Website bearbeiten** " die Werte für die Einstellungen dieser Netzwerk Website entsprechend.

7. Klicken Sie auf **Commit ausführen**.

8. Zum Abschließen der Änderung von Netzwerkstandorten wiederholen Sie die Schritte 4 bis 7 mit Einstellungen für weitere Standorte.

## <a name="associate-a-subnet-with-a-network-site"></a>Zuordnen eines Subnetzes zu einem Netzwerkstandort
<a name="BKMK_AssociateSubnets"> </a>

Jedes Subnetz in Ihrem Netzwerk muss einem bestimmten Netzwerkstandort zugeordnet sein, da mithilfe von Subnetzinformationen der Netzwerkstandort ermittelt wird, an dem sich ein Endpunkt befindet, während eine neuen Sitzung initiiert wird. Wenn die Position jeder Partei in einer Sitzung bekannt ist, können erweiterte Enterprise-VoIP-Features diese Informationen anwenden, um festzulegen, wie die Anrufeinrichtung oder das Routing gehandhabt werden soll.

Alle konfigurierten öffentlichen IP-Adressen der Audio-Video-Edgeserver in Ihrer Bereitstellung müssen den Netzwerkkonfigurationseinstellungen hinzugefügt werden. Diese IP-Adressen werden als Subnetze mit der Maske 32 hinzugefügt. Der zugeordnete Netzwerkstandort muss dem jeweiligen konfigurierten Netzwerkstandort entsprechen. Beispielsweise wäre die öffentliche IP-Adresse, die dem A/V-Edgedienst auf dem zentralen Standort Chicago entspricht, NetworkSiteID Chicago.

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a>So ordnen Sie ein Subnetz mithilfe der Skype for Business Server-Verwaltungsshell einer Netzwerk Website zu

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

2. Führen Sie das Cmdlet **New-CsNetworkSubnet** aus, um ein Subnetz einem Netzwerkstandort zuzuordnen:

   ```
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    Beispiel:

   ```
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    In diesem Beispiel haben Sie eine Zuordnung zwischen dem Subnetz 172.11.12.13 und der Netzwerk Website "Chicago" erstellt.

3. Wiederholen Sie Schritt 2 für alle Subnetze in der Topologie.

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>So ordnen Sie Subnetze durch Importieren einer CSV-Datei Netzwerkstandorten zu

1. Erstellen Sie eine CSV-Datei, die alle Subnetze enthält, die Sie hinzufügen möchten. Erstellen Sie beispielsweise die Datei **Subnetz.csv** mit folgendem Inhalt:

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

3. Führen Sie das folgende Cmdlet aus, um **Subnet. CSV**zu importieren, und speichern Sie dann den Inhalt im lync Server-Verwaltungsspeicher:

   ```
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a>So ordnen Sie ein Subnetz mithilfe der Skype for Business Server-Systemsteuerung einer Netzwerk Website zu

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3. Klicken Sie auf die Navigationsschaltfläche **Subnetz**.

4. Klicken Sie auf **Neu**.

5. Klicken Sie auf der Seite **Neues Subnetz** auf **Subnetz-ID** und geben Sie dann die erste Adresse in den IP-Adressbereich ein, der von dem Subnetz definiert wird, das Sie einem Netzwerkstandort zuordnen möchten.

6. Klicken Sie auf **Maske** und geben Sie die Bitmaske für das Subnetz ein.

7. Klicken Sie auf **Netzwerkstandort-ID** und wählen Sie die Standort-ID des Standorts aus, dem Sie dieses Subnetz hinzufügen.

    > [!NOTE]
    > Wenn Sie noch keine Netzwerkstandorte erstellt haben, ist diese Liste leer. Ausführliche Informationen zu dem Verfahren finden Sie unter [Create or Modify a Network Site](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx). Sie können auch Standort-IDs für Ihre Bereitstellung abrufen, indem Sie das Cmdlet **Get-CsNetworkSite** ausführen. Ausführliche Informationen finden Sie in der Dokumentation zur Skype for Business Server-Verwaltungsshell.

8. Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Subnetzes ein.

9. Klicken Sie auf **Commit ausführen**.

Wiederholen Sie diese Schritte, um einem Netzwerkstandort weitere Subnetze hinzuzufügen.
> [!NOTE]
> Es wird eine Warnung zur Schlüssel Integritäts Anzeige (Khi) ausgelöst, die eine Liste der IP-Adressen angibt, die in Ihrem Netzwerk vorhanden sind, aber keinem Subnetz zugeordnet sind, oder das Subnetz, das die IP-Adressen enthält, nicht mit einer Netzwerk Website verknüpft ist. Diese Benachrichtigung wird innerhalb eines Zeitraums von 8 Stunden nicht mehrmals ausgelöst.

Die relevanten Warnungsinformationen und ein Beispiel lauten wie folgt:

 **Quelle**: CS-Bandbreitenrichtliniendienst (Core)

 **Ereignisnummer**: 36034

 **Ebene**: 2

 **Beschreibung**: die Subnetze für die folgenden IP- \<Adressen: die Liste\> der IP-Adressen ist entweder nicht konfiguriert, oder die Subnetze sind nicht mit einer Netzwerk Website verbunden.

 **Ursache**: Die Subnetze für die zugehörigen IP-Adressen fehlen in den Netzwerkkonfigurationseinstellungen oder die Subnetze sind keinem Netzwerkstandort zugeordnet.

 **Lösung**: Fügen Sie gemäß der IP-Adressenliste den Netzwerkkonfigurationseinstellungen Subnetze hinzu und ordnen Sie jedes Subnetz einem Netzwerkstandort zu.

Wenn die Liste der IP-Adressen beispielsweise die Einträge 10.121.248.226 und 10.121.249.20 enthält, sind diese IP-Adressen entweder keinem Subnetz zugeordnet oder das zugeordnete Subnetz gehört keinem Netzwerkstandort an. Wenn die zugehörigen Subnetze für diese Adressen 10.121.248.0/24 und 10.121.249.0/24 lauten, können Sie das Problem wie folgt lösen:

1. Stellen Sie sicher, dass die IP-Adresse 10.121.248.226 dem Subnetz 10.121.248.0/24 und die IP-Adresse 10.121.249.20 dem Subnetz 10.121.249.0/24 zugeordnet ist.

2. Stellen Sie sicher, dass die Subnetze 10.121.248.0/24 und 10.121.249.0/24 jeweils einem Netzwerkstandort zugeordnet sind.

## <a name="see-also"></a>Siehe auch
<a name="BKMK_AssociateSubnets"> </a>


[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)


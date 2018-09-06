---
title: Bereitstellen von netzwerkregionen, Standorten und Subnetzen in Skype für Unternehmen
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 'Erstellen oder Ändern von netzwerkregionen, Netzwerkstandorten, und ordnen Sie Subnetze in Skype Netzwerk für Business Server. Alle diese für den erweiterten Enterprise-VoIP-Funktionen verwendet werden: Medien umgehen, call Admission Control und Standortbasierte Weiterleitung.'
ms.openlocfilehash: c4598a1a8ffd46412ce16992788af060e5df0b98
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260405"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a>Bereitstellen von netzwerkregionen, Standorten und Subnetzen in Skype für Unternehmen

Erstellen oder Ändern von netzwerkregionen, Netzwerkstandorten, und ordnen Sie Subnetze in Skype Netzwerk für Business Server. Alle diese für den erweiterten Enterprise-VoIP-Funktionen verwendet werden: Medien umgehen, call Admission Control und Standortbasierte Weiterleitung.

Die erweiterten Enterprise-VoIP-Funktionen sind [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [ location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md) und [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md). Für alle diese Funktionen müssen Sie Netzwerkregionen, Netzwerkstandorte und Subnetze erstellen. Beispiel: Für alle diese Funktionen ist es erforderlich, dass jedes Subnetz in Ihrer Topologie einem bestimmten Netzwerkstandort und jeder Netzwerkstandort einer Netzwerkregion zugeordnet ist. Weitere Informationen zu dieser Begriffe finden Sie unter [Netzwerkeinstellungen für den erweiterten Enterprise-VoIP-Funktionen in Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)

Für die Anrufsteuerung und E9-1-1 gelten bei den Netzwerkstandorten zusätzliche Konfigurationsanforderungen:

- Die Anrufsteuerung erfordert, dass ein Bandbreitenrichtlinienprofil für jeden Standort angegeben wird, für den WAN-Bandbreiteneinschränkungen gelten. Wenn Sie die anrufsteuerung bereitstellen möchten, müssen Sie vor dem Konfigurieren von Netzwerkstandorten [bandbreitenrichtlinienprofile in Skype für Business Server erstellen](create-bandwidth-policy-profiles.md) .

- Für E9-1-1 ist es erforderlich, dass für jeden Standort eine Standortrichtlinie angegeben ist. Wenn Sie E9-1-1 bereitstellen möchten, müssen Sie vor dem Konfigurieren von Netzwerkstandorten [Standortrichtlinien in Skype für Business Server erstellen](create-location-policies.md) .

## <a name="create-or-modify-a-network-region"></a>Erstellen oder Ändern einer Netzwerkregion

Wenn Sie bereits von netzwerkregionen für eines der folgenden Features erstellt haben, müssen Sie keine neuen netzwerkregionen zu erstellen; andere erweiterten Enterprise-VoIP-Funktionen werden die gleichen netzwerkregionen verwenden.

Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben.

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a>So erstellen Sie eine netzwerkregion mithilfe der Skype für Business Server-Verwaltungsshell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

2. Führen Sie das Cmdlet New-CsNetworkRegion aus, um Netzwerkregionen zu erstellen:

   ```
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Beispiel:

   ```
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    In diesem Beispiel wird eine netzwerkregion namens "NorthAmerica" erstellt haben, einer zentralen Website mit Website-ID "Chicago" zugeordnet ist.

3. Zum Abschließen der Erstellung von Netzwerkregionen für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Netzwerkregionen.

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a>So erstellen Sie eine netzwerkregion mithilfe der Skype für Business Server-Systemsteuerung

1. Öffnen von Skype Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3. Klicken Sie auf **Region**.

4. Klicken Sie auf **Neu**.

5. Klicken Sie auf der Seite **Neue Region** auf **Name** und geben Sie einen Namen für die Netzwerkregion ein.

6. Klicken Sie auf **Zentraler Standort** und anschließend auf einen zentralen Standort in der Liste.

7. Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Netzwerkstandorts ein.

8. Klicken Sie auf **Commit ausführen**.

9. Zum Abschließen der Erstellung von Netzwerkregionen für Ihre Topologie wiederholen Sie die Schritte 4 bis 8 mit Einstellungen für weitere Regionen.

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a>So ändern Sie eine netzwerkregion mithilfe der Skype für Business Server-Verwaltungsshell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

2. Führen Sie das Cmdlet Set-CsNetworkRegion aus, um eine vorhandene Netzwerkregion zu ändern:

   ```
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Beispiel:

   ```
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    In diesem Beispiel können Sie durch Ändern der Beschreibung eine vorhandenen netzwerkregion namens "NorthAmerica" (mit den Verfahren in diesem Thema erstellt) geändert. Wenn eine Beschreibung für die Region "Nordamerika" vorhanden ist, überschreibt dieser Befehl es mit diesem Wert. Wenn keine Beschreibung festgelegt wurde hatte, wird mit diesem Befehl es aus.

3. Zum Ändern weiterer Netzwerkregionen wiederholen Sie Schritt 2 mit Einstellungen für andere Regionen.

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a>So ändern Sie eine netzwerkregion mithilfe der Skype für Business Server-Systemsteuerung

1. Öffnen von Skype Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3. Klicken Sie auf die Navigationsschaltfläche **Region**.

4. Klicken Sie in der Tabelle auf die Netzwerkregion, die Sie ändern möchten.

5. Klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.

6. Ändern Sie auf der Seite **Region bearbeiten** die Werte für diese netzwerkregion Einstellungen wie gewünscht ab.

7. Klicken Sie auf **Commit ausführen**.

8. Zum Abschließen der Änderung von Netzwerkregionen wiederholen Sie die Schritte 4 bis 7 mit Einstellungen für weitere Regionen.

## <a name="create-or-modify-a-network-site"></a>Erstellen oder Ändern eines Netzwerkstandorts

Wenn Sie Netzwerkstandorte für eines der folgenden Features bereits erstellt haben, müssen Sie keine neuen Netzwerkstandorten erstellen; andere erweiterten Enterprise-VoIP-Funktionen werden die gleichen Netzwerkstandorten verwenden. Sie müssen jedoch möglicherweise eine vorhandene Definition eines Netzwerkstandorts ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. einen Netzwerkstandort für E9-1-1 erstellt haben, müssen Sie den Netzwerkstandort während der Bereitstellung der Anrufsteuerung ändern, um ein Bandbreitenrichtlinienprofil anzuwenden.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a>Erstellen Sie einen Netzwerkstandort mithilfe von Skype für Business Server-Verwaltungsshell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

2. Führen Sie das Cmdlet New-CsNetworkSite aus, um Netzwerkstandorte zu erstellen:

   ```
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    Beispiel:

   ```
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    In diesem Beispiel wird einen Netzwerkstandort namens "Chicago" erstellt haben, ist in der netzwerkregion "NorthAmerica befindet".

    > [!NOTE]
    > Die Netzwerkregion „NorthAmerica“ muss bereits vorhanden sein, damit dieser Befehl erfolgreich ausgeführt werden kann.

3. Zum Abschließen der Erstellung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a>Einen Netzwerkstandort mithilfe von Skype Business Server-Systemsteuerung erstellen

1. Öffnen von Skype Business Server-Systemsteuerung.

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

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a>So ändern Sie einen Netzwerkstandort mithilfe von Skype für Business Server-Verwaltungsshell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

2. Führen Sie das Cmdlet Set-CsNetworkSite aus, um Netzwerkstandorte zu ändern:

   ```
   Set-CsNetworkSite -Identity <string>
   ```

    Beispiel:

   ```
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    In diesem Beispiel wird die Website aufgerufen "Albuquerque" in der netzwerkregion "NorthAmerica" verschoben. Bearbeiten Sie zum Ändern der Netzwerkstandortkonfiguration für die Bereitstellung von Anrufsteuerung, E9-1-1 oder Medienumgehung die Netzwerkstandorteinstellungen, indem Sie das Cmdlet Set-CsNetworkSite mit dem Parameter BWPolicyProfileID oder LocationPolicy ausführen.

    > [!NOTE]
    > Wenngleich der Parameter BypassID für die Medienumgehung vorhanden ist, wird dringend empfohlen, automatisch generierte IDs für die Umgehung nicht außer Kraft zu setzen. Sie müssen keine zusätzlichen Parameter angeben, um einen Netzwerkstandort für die Medienumgehung zu konfigurieren.

3. Zum Abschließen der Änderung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a>So ändern Sie einen Netzwerkstandort mithilfe von Skype Business Server-Systemsteuerung

1. Öffnen von Skype Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3. Klicken Sie auf die Navigationsschaltfläche **Standort**.

4. Klicken Sie in der Tabelle auf den Netzwerkstandort, den Sie ändern möchten.

5. Klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.

6. Ändern Sie auf der Seite **Standort bearbeiten** die Werte für dieses Netzwerkstandorts Einstellungen wie gewünscht ab.

7. Klicken Sie auf **Commit ausführen**.

8. Zum Abschließen der Änderung von Netzwerkstandorten wiederholen Sie die Schritte 4 bis 7 mit Einstellungen für weitere Standorte.

## <a name="associate-a-subnet-with-a-network-site"></a>Zuordnen eines Subnetzes zu einem Netzwerkstandort
<a name="BKMK_AssociateSubnets"> </a>

Jedes Subnetz in Ihrem Netzwerk muss einem bestimmten Netzwerkstandort zugeordnet sein, da mithilfe von Subnetzinformationen der Netzwerkstandort ermittelt wird, an dem sich ein Endpunkt befindet, während eine neuen Sitzung initiiert wird. Wenn Sie der Speicherort der einzelnen Parteien in einer Sitzung bekannt ist, routing oder erweiterte Enterprise-VoIP-Funktionen können anwenden, Informationen zur Bestimmung der Einrichtung des Anrufs Behandlung von.

Alle konfigurierten öffentlichen IP-Adressen der Audio-Video-Edgeserver in Ihrer Bereitstellung müssen den Netzwerkkonfigurationseinstellungen hinzugefügt werden. Diese IP-Adressen werden als Subnetze mit der Maske 32 hinzugefügt. Der zugeordnete Netzwerkstandort muss dem jeweiligen konfigurierten Netzwerkstandort entsprechen. Angenommen, die öffentliche IP-Adresse, die dem A entspricht / V-edgedienst im zentralen Standort Chicago wäre NetworkSiteID Chicago.

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a>Um ein Subnetz einem Netzwerkstandort zuzuordnen mithilfe von Skype für Business Server-Verwaltungsshell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

2. Führen Sie das Cmdlet **New-csnetworksubnet aus** , um ein Subnetz einem Netzwerkstandort zuzuordnen:

   ```
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    Beispiel:

   ```
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

2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

3. Führen Sie zum Importieren der **Datei Subnetz.csv**das folgende Cmdlet aus, und speichern Sie ihren Inhalt im Verwaltungsspeicher von Lync Server:

   ```
   import-csv subnet.csv | foreach {New-CsNetworkSubnet $_IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a>Um ein Subnetz mithilfe von Skype Business Server-Systemsteuerung einem Netzwerkstandort zuzuordnen

1. Öffnen von Skype Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3. Klicken Sie auf die Navigationsschaltfläche **Subnetz**.

4. Klicken Sie auf **Neu**.

5. Klicken Sie auf der Seite **Neues Subnetz** auf **Subnetz-ID** und geben Sie dann die erste Adresse in den IP-Adressbereich ein, der von dem Subnetz definiert wird, das Sie einem Netzwerkstandort zuordnen möchten.

6. Klicken Sie auf **Maske** und geben Sie die Bitmaske für das Subnetz ein.

7. Klicken Sie auf **Netzwerkstandort-ID** und wählen Sie die Standort-ID des Standorts aus, dem Sie dieses Subnetz hinzufügen.

    > [!NOTE]
    > Wenn Sie noch keine Netzwerkstandorte erstellt haben, ist diese Liste leer. Ausführliche Informationen über das Verfahren finden Sie unter [Erstellen oder Ändern eines Netzwerkstandorts](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx). Sie können auch Site-IDs für Ihre Bereitstellung durch Ausführen des Cmdlets **Get-CsNetworkSite** abrufen. Weitere Informationen hierzu finden Sie unter der Skype Business Server-Verwaltungsshell-Dokumentation.

8. Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Subnetzes ein.

9. Klicken Sie auf **Commit ausführen**.

Wiederholen Sie diese Schritte, um einem Netzwerkstandort weitere Subnetze hinzuzufügen.
> [!NOTE]
> Eine Warnung Key Health Indicator (KHI) wird ausgelöst, Angeben einer Liste von IP-Adressen, die in Ihrem Netzwerk vorhanden sind, aber entweder nicht zugeordnet sind ein Subnetz, oder das Subnetz, das die IP-Adressen ist keinem Netzwerkstandort zugeordnet. Diese Warnung wird innerhalb einer 8-Stunden-Zeitraum nicht mehr als einmal ausgelöst werden.

Die entsprechenden alert Informationen und ein Beispiel lauten wie folgt:

 **Quelle**: CS-Bandbreitenrichtliniendienst (Core)

 **Ereignisnummer**: 36034

 **Ebene**: 2

 **Beschreibung**: die Subnetze für die folgenden IP-Adressen: \<Liste der IP-Adressen\> ist entweder nicht konfiguriert oder die Subnetze sind keinem Netzwerkstandort zugeordnet.

 **Ursache**: Die Subnetze für die zugehörigen IP-Adressen fehlen in den Netzwerkkonfigurationseinstellungen oder die Subnetze sind keinem Netzwerkstandort zugeordnet.

 **Lösung**: Fügen Sie gemäß der IP-Adressenliste den Netzwerkkonfigurationseinstellungen Subnetze hinzu und ordnen Sie jedes Subnetz einem Netzwerkstandort zu.

Wenn die Liste der IP-Adressen beispielsweise die Einträge 10.121.248.226 und 10.121.249.20 enthält, sind diese IP-Adressen entweder keinem Subnetz zugeordnet oder das zugeordnete Subnetz gehört keinem Netzwerkstandort an. Wenn die zugehörigen Subnetze für diese Adressen 10.121.248.0/24 und 10.121.249.0/24 lauten, können Sie das Problem wie folgt lösen:

1. Stellen Sie sicher, dass die IP-Adresse 10.121.248.226 dem Subnetz 10.121.248.0/24 und die IP-Adresse 10.121.249.20 dem Subnetz 10.121.249.0/24 zugeordnet ist.

2. Stellen Sie sicher, dass die Subnetze 10.121.248.0/24 und 10.121.249.0/24 jeweils einem Netzwerkstandort zugeordnet sind.

## <a name="see-also"></a>Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.
<a name="BKMK_AssociateSubnets"> </a>


[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)


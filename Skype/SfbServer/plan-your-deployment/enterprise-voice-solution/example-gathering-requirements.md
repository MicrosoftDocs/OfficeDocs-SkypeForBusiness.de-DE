---
title: Beispielsammlungsanforderungen für die Anrufsteuerung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
description: Enthält ein detailliertes Beispiel für die Planung der Anrufsteuerung in Skype for Business Server Enterprise-VoIP, einschließlich der Erfassung von Informationen zu Standorten, Regionen und Bandbreite Ihres Netzwerks.
ms.openlocfilehash: a51ffe9248a8d5daf1e21a9c20bb753ddb26898f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825685"
---
# <a name="example-gathering-requirements-for-call-admission-control-in-skype-for-business-server"></a>Beispiel: Sammeln von Anforderungen für die Anrufsteuerung in Skype for Business Server

Enthält ein detailliertes Beispiel für die Planung der Anrufsteuerung in Skype for Business Server Enterprise-VoIP, einschließlich der Erfassung von Informationen zu Standorten, Regionen und Bandbreite Ihres Netzwerks.

Dieses Beispiel führt Sie Schritt für Schritt durch die Planung und Implementierung der Anrufsteuerungsdiensts (Call Admission Control, CAC). Bei diesem Verfahren werden die folgenden allgemeinen Aufgaben ausgeführt:

1. Identifizieren aller Netzwerkhubs und Backbones (als Netzwerkregionen bezeichnet).

2. Identifizieren Sie den zentralen Skype for Business Server-Standort, der die Anrufanrufe für jede Netzwerkregion verwaltet.

3. Identifizieren und Definieren der Netzwerkstandorte, die mit jeder Netzwerkregion verbunden sind.

4. Beschreiben Sie für jeden Netzwerkstandort, dessen Verbindung mit dem WAN bandbreitenbeschränkungen ist, die Bandbreitenkapazität der WAN-Verbindung und die Bandbreitenbeschränkungen, die der Netzwerkadministrator für den Skype for Business Server-Mediendatenverkehr festgelegt hat, falls zutreffend. Standorte mit WAN-Verbindungen ohne Bandbreiteneinschränkung müssen nicht einbezogen werden.

5. Zuordnen der einzelnen Subnetze in Ihrem Netzwerk zu einem Netzwerkstandort.

6. Zuordnen der Verbindungen zwischen den Netzwerkregionen. Beschreiben Sie für jede Verbindung die Bandbreitenkapazität und alle Grenzwerte, die der Netzwerkadministrator für den Skype for Business Server-Mediendatenverkehr festgelegt hat.

7. Definieren einer Route zwischen jedem Netzwerkregionenpaar.

## <a name="gather-the-required-information"></a>Sammeln der erforderlichen Informationen

Zur Vorbereitung der Anrufsteuerung müssen Sie die in den folgenden Schritten beschriebenen Informationen sammeln:

1. Identifizieren Sie Ihre Netzwerkregionen. Eine Netzwerkregion repräsentiert einen Netzwerkbackbone oder einen Netzwerkhub. 

    Ein Netzwerkbackbone oder ein Netzwerkhub ist Bestandteil der Computernetzwerkinfrastruktur, die verschiedene Komponenten im Netzwerk verbindet und einen Pfad für den Austausch von Informationen zwischen unterschiedlichen LANs oder Subnetzen bereitstellt. Ein Backbone kann unterschiedliche Netzwerke miteinander verknüpfen, von kleinen Standorten bis hin zu einem geografisch weit verteilten Bereich. Die Kapazität des Backbones ist in der Regel höher als die der Netzwerke, die mit ihm verbunden sind.

    Die hier vorgestellte Beispieltopologie umfasst drei Netzwerkregionen: Nordamerika, EMEA und APAC. Eine Netzwerkregion enthält verschiedene Netzwerkstandorte. Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um die Netzwerkregionen für Ihr Unternehmen zu definieren.

2. Identifizieren Sie den zugeordneten zentralen Standort jeder Netzwerkregion. Ein zentraler Standort enthält mindestens einen Front-End-Server und ist die Skype for Business Server-Bereitstellung, die die Anrufbeoheit für den mediendatenverkehr verwaltet, der die WAN-Verbindung der Netzwerkregion durchläuft.

   **Beispielunternehmensnetzwerk mit drei Netzwerkregionen**

     ![Beispiel für eine Netzwerktopologie mit drei Netzwerkregionen](../../media/Plan_CS_VoiceCAC_example3networkregions.jpg)

    > [!NOTE]
    > Ein MPLS-Netzwerk (Multiprotocol Label Switching) sollte als Netzwerkregion abgebildet werden, bei der jeder geografische Standort über einen entsprechenden Netzwerkstandort verfügt. Weitere Informationen finden Sie unter ["Komponenten und Topologien für die Anrufsteuerung in Skype for Business".](components-and-topologies.md) 

    In der oben genannten Beispielnetzwerktopologie gibt es drei Netzwerkregionen, die jeweils über einen zentralen Skype for Business Server-Standort für die Verwaltung der Anrufanrufe vorhanden sind. Der geeignete zentrale Standort für eine Netzwerkregion wird nach geografischer Nähe ausgewählt. Da innerhalb der Netzwerkregionen das Aufkommen an Mediendatenverkehr am höchsten ist, führt die Festlegung nach geografischer Nähe zu einer eigenständigen Konfiguration, die auch dann noch funktionsfähig ist, wenn andere zentrale Standorte ausfallen. 

    In diesem Beispiel ist eine Skype for Business-Bereitstellung mit dem Namen "Chicago" der zentrale Standort für die Region "Nordamerika".

    Alle Skype for Business-Benutzer in Nordamerika werden auf Servern in der Bereitstellung von Chicago gespeichert. Die folgende Tabelle zeigt die zentralen Standorte für alle drei Netzwerkregionen.

    **Netzwerkregionen und zugeordnete zentrale Standorte**

    |**Netzwerkregion**|**Zentraler Standort**|
    |:-----|:-----|
    |Nordamerika  <br/> |Chicago  <br/> |
    |EMEA  <br/> |London  <br/> |
    |APAC  <br/> |Beijing  <br/> |

    > [!NOTE]
    > Je nach Skype for Business Server-Topologie kann derselbe zentrale Standort mehreren Netzwerkregionen zugewiesen werden. 

3. Identifizieren Sie für jede Netzwerkregion alle Netzwerkstandorte (Büros oder Zweigstellen), für deren WAN-Verbindungen keine Bandbreiteneinschränkungen gelten. Da diese Standorte keine Bandbreiteneinschränkungen aufweisen, müssen keine Richtlinien für die Anrufsteuerung auf sie angewendet werden.

    Im Beispiel in der folgenden Tabelle gibt es drei Netzwerkstandorte, deren WAN-Verbindungen keine Bandbreiteneinschränkungen aufweisen: "New York", "Chicago" und "Detroit".

   **Netzwerkstandorte ohne Einschränkungen in Bezug auf die WAN-Bandbreite**


   | **Netzwerkstandort** | **Netzwerkregion**   |
   |:-----------------|:---------------------|
   | New York  <br/>  | Nordamerika  <br/> |
   | Chicago  <br/>   | Nordamerika  <br/> |
   | Detroit  <br/>   | Nordamerika  <br/> |


4. Identifizieren Sie für jede Netzwerkregion alle Netzwerkstandorte, die über WAN-Verbindungen mit Bandbreiteneinschränkungen eine Verbindung mit der Netzwerkregion herstellen.

    Um die Audio- und Videoqualität besser sicherstellen zu können, wird für diese Netzwerkstandorte mit Bandbreiteneinschränkungen empfohlen, die WAN-Verbindungen zu überwachen und Richtlinien für die Anrufsteuerung anzuwenden, um den Mediendatenverkehr (Sprache oder Video) von und zu der Netzwerkregion zu beschränken.

    Im Beispiel in der folgenden Tabelle sind drei Netzwerkstandorte vorhanden, deren WAN-Bandbreite eingeschränkt ist: "Portland", "Reno" und "Albuquerque".

   **Netzwerkstandorte mit Einschränkungen in Bezug auf die WAN-Bandbreite**

   |**Netzwerkstandort**|**Netzwerkregion**|
   |:-----|:-----|
   |Albuquerque  <br/> |Nordamerika  <br/> |
   |Reno  <br/> |Nordamerika  <br/> |
   |Portland  <br/> |Nordamerika  <br/> |

   **Anrufsteuerung in der Netzwerkregion "Nordamerika" mit drei Netzwerkstandorten, die keine Bandbreiteneinschränkung aufweisen (Chicago, New York und Detroit), und drei Netzwerkstandorten mit eingeschränkter WAN-Bandbreite (Portland, Reno und Albuquerque)**

     ![Beispiel für Netzwerkstandorte, beschränkt durch die WAN-Bandbreite](../../media/Plan_CS_VoiceCAC_comparisonof6regionsandconstraints.jpg)

5. Ermitteln Sie für jede WAN-Verbindung mit eingeschränkter Bandbreite die folgenden Informationen:

   - Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Audiositzungen festlegen möchten. Wenn eine neue Audiositzung dazu führt, dass dieser Grenzwert überschritten wird, lässt Skype for Business Server den Start der Sitzung nicht zu.

   - Bandbreiteneinschränkung, die Sie für jede einzelne Audiositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 175 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.

   - Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Videositzungen festlegen möchten. Wenn eine neue Videositzung dazu führt, dass dieser Grenzwert überschritten wird, lässt Skype for Business Server den Start der Sitzung nicht zu.

   - Bandbreiteneinschränkung, die Sie für jede einzelne Videositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 700 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.

     **Netzwerkstandorte mit Informationen zur WAN-Bandbreiteneinschränkung (Bandbreite in KBit/s)**


     | **Netzwerkstandort**   | **Netzwerkregion**   | **Grenzwert für Bandbreite**      | **Grenzwert für Audio**   | **Grenzwert für Audiositzung** | **Grenzwert für Video**   | **Grenzwert für Videositzung** |
     |:-------------------|:---------------------|:------------------|:------------------|:------------------------|:------------------|:------------------------|
     | Albuquerque  <br/> | Nordamerika  <br/> | 5,000  <br/>      | 2,000  <br/>      | 175  <br/>              | 1,400  <br/>      | 700  <br/>              |
     | Reno  <br/>        | Nordamerika  <br/> | 10.000  <br/>     | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              |
     | Portland  <br/>    | Nordamerika  <br/> | 5,000  <br/>      | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              |
     | New York  <br/>    | Nordamerika  <br/> | (keine Begrenzung)  <br/> | (keine Begrenzung)  <br/> | (keine Begrenzung)  <br/>       | (keine Begrenzung)  <br/> | (keine Begrenzung)  <br/>       |
     | Chicago  <br/>     | Nordamerika  <br/> | (keine Begrenzung)  <br/> | (keine Begrenzung)  <br/> | (keine Begrenzung)  <br/>       | (keine Begrenzung)  <br/> | (keine Begrenzung)  <br/>       |
     | Detroit  <br/>     | Nordamerika  <br/> | (keine Begrenzung)  <br/> | (keine Begrenzung)  <br/> | (keine Begrenzung)  <br/>       | (keine Begrenzung)  <br/> | (keine Begrenzung)  <br/>       |


6. Geben Sie für jedes Subnetz in Ihrem Netzwerk den zugeordneten Netzwerkstandort an.

    > [!IMPORTANT]
    > Jedes Subnetz in Ihrem Netzwerk muss einem Netzwerkstandort zugeordnet sein – selbst dann, wenn für den Netzwerkstandort keine Bandbreiteneinschränkungen gelten. Diese Anforderung gilt, da die Anrufsteuerung mithilfe von Subnetzinformationen ermittelt, an welchem Netzwerkstandort sich ein Endpunkt befindet. Wenn die Standorte beider Sitzungsteilnehmer ermittelt wurden, kann über die Anrufsteuerung festgestellt werden, ob genügend Bandbreite für einen Anruf vorhanden ist. Wird eine Sitzung über eine Verbindung ohne Bandbreiteneinschränkungen hergestellt, wird eine Warnung generiert. 

    > [!IMPORTANT]
    > Wenn Sie A/V-Edgeserver (Audio/Video) bereitstellen, müssen die öffentlichen IP-Adressen der jeweiligen Edgeserver dem Netzwerkstandort zugeordnet werden, in dem der Edgeserver bereitgestellt wurde. Jede öffentliche IP-Adresse des A/V-Edgeservers muss in den Netzwerkkonfigurationseinstellungen als Subnetz mit der Subnetzmaske 32 hinzugefügt werden. Wenn Sie beispielsweise A/V-Edgeserver in Chicago bereitstellen, müssen Sie für jede externe IP-Adresse dieser Server ein Subnetz mit der Subnetzmaske 32 erstellen und Netzwerkstandort "Chicago" diesen Subnetzen zuordnen. Weitere Informationen zu öffentlichen IP-Adressen finden Sie unter ["Planen der Netzwerkanforderungen für Skype for Business".](../../plan-your-deployment/network-requirements/network-requirements.md) 

    Es wird eine KHI-Warnung (Key Health Indicator) ausgegeben. Diese enthält eine Liste der IP-Adressen, die in Ihrem Netzwerk vorhanden, aber keinem Subnetz zugeordnet sind, oder gibt das Subnetz an, das die IP-Adressen enthält, jedoch keinem Netzwerkstandort zugeordnet ist. Diese Warnung wird innerhalb von 8 Stunden nur einmal angezeigt. Nachfolgend finden Sie die relevanten Warnungsinformationen und ein Beispiel:

    **Quelle**: CS-Bandbreitenrichtliniendienst (Core) 

    **Ereignisnummer**: 36034

    **Ebene**: 2

    **Beschreibung:** Die Subnetze für die folgenden IP-Adressen: sind entweder nicht konfiguriert oder die Subnetze \<List of IP Addresses\> sind keinem Netzwerkstandort zugeordnet. 

    **Ursache**: Die Subnetze für die zugehörigen IP-Adressen fehlen in den Netzwerkkonfigurationseinstellungen, oder die Subnetze sind keinem Netzwerkstandort zugeordnet. 

    **Lösung**: Fügen Sie gemäß der IP-Adressenliste den Netzwerkkonfigurationseinstellungen Subnetze hinzu, und ordnen Sie jedes Subnetz einem Netzwerkstandort zu.

    Wenn die Liste der IP-Adressen beispielsweise die Einträge 10.121.248.226 und 10.121.249.20 enthält, sind diese IP-Adressen entweder keinem Subnetz zugeordnet, oder das zugeordnete Subnetz gehört keinem Netzwerkstandort an. Wenn die zugehörigen Subnetze für diese Adressen 10.121.248.0/24 und 10.121.249.0/24 lauten, können Sie das Problem wie folgt lösen:

    a. Stellen Sie sicher, dass die IP-Adresse 10.121.248.226 dem Subnetz 10.121.248.0/24 und die IP-Adresse 10.121.249.20 dem Subnetz 10.121.249.0/24 zugeordnet ist.

    b. Stellen Sie sicher, dass die Subnetze 10.121.248.0/24 und 10.121.249.0/24 jeweils einem Netzwerkstandort zugeordnet sind.

   **Netzwerkstandorte und zugeordnete Subnetze (Bandbreite in KBit/s)**


   | **Netzwerkstandort**   | **Netzwerkregion**   | **Grenzwert für Bandbreite**      | **Grenzwert für Audio**   | **Grenzwert für Audiositzung** | **Grenzwert für Video**   | **Grenzwert für Videositzung** | **Subnetze**                                                            |
   |:-------------------|:---------------------|:------------------|:------------------|:------------------------|:------------------|:------------------------|:-----------------------------------------------------------------------|
   | Albuquerque  <br/> | Nordamerika  <br/> | 5,000  <br/>      | 2,000  <br/>      | 175  <br/>              | 1,400  <br/>      | 700  <br/>              | 172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24  <br/> |
   | Reno  <br/>        | Nordamerika  <br/> | 10.000  <br/>     | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              | 157.57.210.0/23, 172.28.151.128/25  <br/>                              |
   | Portland  <br/>    | Nordamerika  <br/> | 5,000  <br/>      | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              | 172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23  <br/>                  |
   | New York  <br/>    | Nordamerika  <br/> | (keine Begrenzung)  <br/> | (keine Begrenzung)  <br/> | (keine Begrenzung)  <br/>       | (keine Begrenzung)  <br/> | (keine Begrenzung)  <br/>       | 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24  <br/> |
   | Chicago  <br/>     | Nordamerika  <br/> | (keine Begrenzung)  <br/> | (keine Begrenzung)  <br/> | (keine Begrenzung)  <br/>       | (keine Begrenzung)  <br/> | (keine Begrenzung)  <br/>       | 157.57.211.0/23, 172.28.152.128/25  <br/>                              |
   | Detroit  <br/>     | Nordamerika  <br/> | (keine Begrenzung)  <br/> | (keine Begrenzung)  <br/> | (keine Begrenzung)  <br/>       | (keine Begrenzung)  <br/> | (keine Begrenzung)  <br/>       | 172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23  <br/>                  |


7. Bei der Anrufsteuerung von Skype for Business Server werden die Verbindungen zwischen Netzwerkregionen als Regionenverbindungen bezeichnet. Ermitteln Sie für jede Regionenverbindung, ebenso wie für die Netzwerkstandorte, die folgenden Informationen:

   - Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Audiositzungen festlegen möchten. Wenn eine neue Audiositzung dazu führt, dass dieser Grenzwert überschritten wird, lässt Skype for Business Server den Start der Sitzung nicht zu.

   - Bandbreiteneinschränkung, die Sie für jede einzelne Audiositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 175 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.

   - Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Videositzungen festlegen möchten. Wenn eine neue Videositzung dazu führt, dass dieser Grenzwert überschritten wird, lässt Skype for Business Server den Start der Sitzung nicht zu.

   - Bandbreiteneinschränkung, die Sie für jede einzelne Videositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 700 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.

   **Netzwerkregionenverbindungen mit zugehörigen Bandbreiteneinschränkungen**

     ![Beispiel für Einschränkungen zwischen 3 Regionen](../../media/Plan_CS_VoiceCAC_limitsbetween3regions.jpg)

   **Bandbreiteninformationen zu Regionenverbindungen (Bandbreite in KBit/s)**


   | **Name der Regionenverbindung**  | **Erste Region**     | **Zweite Region** | **Grenzwert für Bandbreite**  | **Grenzwert für Audio** | **Grenzwert für Audiositzung** | **Grenzwert für Video** | **Grenzwert für Videositzung** |
   |:----------------------|:---------------------|:------------------|:--------------|:----------------|:------------------------|:----------------|:------------------------|
   | NA-EMEA-LINK  <br/>   | Nordamerika  <br/> | EMEA  <br/>       | 50.000  <br/> | 20,000  <br/>   | 175  <br/>              | 14,000  <br/>   | 700  <br/>              |
   | EMEA-APAC-LINK  <br/> | EMEA  <br/>          | APAC  <br/>       | 25.000  <br/> | 10.000  <br/>   | 175  <br/>              | 7,000  <br/>    | 700  <br/>              |


8. Definieren einer Route zwischen jedem Netzwerkregionenpaar.

    > [!NOTE]
    > Für die Route zwischen den Regionen "Nordamerika" und "APAC" sind zwei Verbindungen erforderlich, da keine Region vorhanden ist, die die Regionen direkt miteinander verbindet. 

   **Routen zwischen Regionen**


   | **Name der Regionenroute**  | **Erste Region**     | **Zweite Region** | **Regionenverbindungen**                    |
   |:-----------------------|:---------------------|:------------------|:------------------------------------|
   | NA-EMEA-ROUTE  <br/>   | Nordamerika  <br/> | EMEA  <br/>       | NA-EMEA-LINK  <br/>                 |
   | EMEA-APAC-ROUTE  <br/> | EMEA  <br/>          | APAC  <br/>       | EMEA-APAC-LINK  <br/>               |
   | NA-APAC-ROUTE  <br/>   | Nordamerika  <br/> | APAC  <br/>       | NA-EMEA-LINK, EMEA-APAC-LINK  <br/> |


9. Ermitteln Sie für jedes Netzwerkstandortpaar, das durch eine einzelne Verbindung direkt miteinander verbunden wird (als standortübergreifende Verbindung bezeichnet), die folgenden Informationen:

     - Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Audiositzungen festlegen möchten. Wenn eine neue Audiositzung dazu führt, dass dieser Grenzwert überschritten wird, lässt Skype for Business Server den Start der Sitzung nicht zu.

     - Bandbreiteneinschränkung, die Sie für jede einzelne Audiositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 175 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.

     - Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Videositzungen festlegen möchten. Wenn eine neue Videositzung dazu führt, dass dieser Grenzwert überschritten wird, lässt Skype for Business Server den Start der Sitzung nicht zu.

     - Bandbreiteneinschränkung, die Sie für jede einzelne Videositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 700 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.

   **Anrufsteuerung in der Netzwerkregion "Nordamerika" mit Anzeige der Bandbreitenkapazitäten und -einschränkungen für die standortübergreifende Verbindung zwischen Reno und Albuquerque**

     ![Beispiel für Netzwerkstandorte mit eingeschränkter WAN-Bandbreite](../../media/Plan_CS_VoiceCAC_limitsforNAdirectlinksRenoAlbuq.jpg)

   **Bandbreiteninformationen für eine standortübergreifende Verbindung zwischen zwei Netzwerkstandorten (Bandbreite in KBit/s)**

   |**Name der standortübergreifenden Verbindung**|**Erster Standort**|**Zweiter Standort**|**Grenzwert für Bandbreite**|**Grenzwert für Audio**|**Grenzwert für Audiositzung**|**Grenzwert für Video**|**Grenzwert für Videositzung**|
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |Reno-Albu-Intersite-Link  <br/> |Reno  <br/> |Albuquerque  <br/> |20,000  <br/> |12,000  <br/> |175  <br/> |5,000  <br/> |700  <br/> |

### <a name="next-steps"></a>Nächste Schritte

Nachdem Sie die erforderlichen Informationen gesammelt haben, können Sie die Anrufsteuerung entweder mithilfe der Skype for Business Server-Verwaltungsshell oder der Skype for Business Server-Systemsteuerung durchführen.

> [!NOTE]
> Obwohl Sie die meisten Netzwerkkonfigurationsaufgaben mithilfe der Skype for Business Server-Systemsteuerung ausführen können, müssen Sie zum Erstellen von Subnetzen und standortübergreifenden Verbindungen die Skype for Business Server-Verwaltungsshell verwenden. Weitere Informationen finden Sie unter ["New-CsNetworkSubnet" und](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps) ["New-CsNetworkInterSitePolicy".](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps) 



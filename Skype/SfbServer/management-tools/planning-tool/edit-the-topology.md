---
title: Bearbeiten der Topologie in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Nachdem Sie die Fragen zum ersten Gespräch beantwortet haben, können Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) und die IP-Adressen für die Website bearbeiten. Doppelklicken Sie hierzu auf der Seite Globale Topologie auf den Standort, den Sie bearbeiten möchten.
ms.openlocfilehash: 9a345c753195c32907d078d5ee4a267b8b96d6b0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093183"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a>Bearbeiten der Topologie in Skype for Business Server 2015

Nachdem Sie die Fragen zum ersten Gespräch beantwortet haben, können Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) und die IP-Adressen für die Website bearbeiten. Doppelklicken Sie hierzu auf der Seite **Globale Topologie** auf den Standort, den Sie bearbeiten möchten.

Das Planungstool zeigt die Websitetopologie für die ausgewählte Website an. Im unteren Bereich der Seite für den Standort werden vier Registerkarten angezeigt:

![Planen der Websitetopologie des Planungstools](../../media/Planning_Tool_Site_Topology.png)

- Websitetopologie – Die derzeit angezeigte Seite mit einer visuellen Übersicht über die Topologie, wie empfohlen.

- Edgenetzwerkdiagramm – Auf der Seite Edgenetzwerkdiagramm wird der Designer die meiste Arbeit im Planungstool durchführen. Das Diagramm zeigt die Netzwerkkonfiguration für eine empfohlene Skype for Business Server 2015-Topologie mit bearbeitbaren Einträgen für IP-Adressen und FQDNs für Server, Pools sowie Hardware- und DNS-Lastenausgleichsgeräte (Domain Name System).

- Edge-Admin-Bericht – Der Edgeadministratorbericht enthält insgesamt vier Berichte:

     ![Seite "Edge-Admin-Bericht"](../../media/Planning_Tool_Summary_Report.png)

  - Zusammenfassungsbericht – Ein allgemeiner Bericht über einstellungen für die Edgenetzwerkkonfiguration. Wenn Sie die Werte auf der Seite **Edgenetzwerkdiagramm** auf die TCP/IP- und FQDN-Werte der Topologie bearbeiten, die in der tatsächlichen Bereitstellung verwendet werden, werden diese Adressen und Namen hier dargestellt. Andernfalls wird der Standardtext angezeigt.

  - Zertifikatbericht – Der Zertifikatbericht listet den Betreffnamen und alternative Namen des Betreffs für die Zertifikate auf, die für die Topologie erforderlich sind.

  - Firewallbericht – Der Firewallbericht enthält Informationen, die zum Konfigurieren von Umkreisfirewalls in der Infrastruktur erforderlich sind. Dazu gehören die IP-Adressen (standard- oder bearbeitete Werte), Serverrolle, Quell-IP und Port, Ziel-IP und -Port, Transportprotokoll, Anwendungsprotokoll und relevante Hinweise.

  - DNS-Bericht – Der DNS-Bericht enthält relevante Informationen für die dns-Einträge, die Sie erstellen müssen. Hierzu zählen Eintragstyp, FQDN, IP-Adresse und Hinweise zum ordnungsgemäßen Betrieb.

- Websitezusammenfassung – Die Websitezusammenfassung enthält eine Übersicht über die Auswahl, die Sie getroffen haben, indem Sie entweder die anfänglichen Fragen zum Vorstellungsgespräch beantworten oder die Werte in **Design Sites ausfüllen.** Kapazitätsinformationen werden ebenfalls dargestellt.

    > [!NOTE]
    > Die Informationen auf der Seite mit der Standortzusammenfassung sind auf den jeweiligen Entwurf zugeschnitten und enthält möglicherweise nicht alle Abschnitte oder Informationen, die hier besprochen werden.

## <a name="edit-the-network-configuration-diagram"></a>Bearbeiten des Netzwerkkonfigurationsdiagramms
<a name="Edit_Network_diagram"> </a>

Der Großteil der Arbeit, die ein Designer im Skype for Business Server 2015-Planungstool vor sich hat, besteht darin, die Einträge für die IP-Adressen und vollqualifizierten Domänennamen (FQDNs) für die Einträge im Netzwerkdiagramm zu definieren. Die informationen, die auf dieser Seite eingegeben werden, werden in die Berichte und andere Informationen im Planungstool weitergeleitet.

![Diagramm "Planungstoolnetzwerk"](../../media/Planning_Tool_Network_Diagram.png)

Das Planungstool erstellt ein Netzwerkdiagramm mit Standardtext für IP-Adressen und FQDNs.

So bearbeiten Sie das Netzwerkdiagramm und geben Werte ein

1. Wählen Sie einen Abschnitt des Netzwerks aus, den Sie bearbeiten möchten. Doppelklicken Sie beispielsweise auf den Text, **access1.contoso.com**. Geben Sie in das geöffnete Dialogfeld den tatsächlichen FQDN des Servers access1.contoso.com und die tatsächliche IP-Adresse ein, und ersetzen Sie dabei den 131.107.155.3.

2. Klicken Sie auf **OK**, um die Einträge zu speichern.

3. Fahren Sie mit der Bearbeitung von IP-Adressen und FQDNs fort, und geben Sie virtuelle IP-Adressen für Hardwaregeräte zum Lastenausgleich oder Servereinträge für einen DNS-Lastenausgleich (Domain Name System) für Server in Pools an.

Eine nützliche Funktion des Planungstools ist die, dass ein Bereich von IP-Adressen und Serverhostnamen inkrementell zugewiesen werden kann. Auf diese Weise muss der für den Entwurf verantwortliche Benutzer die Server in einem Pool nicht einzeln bearbeiten. Beispiel:

1. Doppelklicken Sie auf die Front-End-Server im Pool. Wählen Sie im nun geöffneten Dialogfeld die Option **Möchten Sie IP-Adressen und FQDN als Startpunkte für alle äquivalenten Server im Cluster verwenden?**.

2. Der Startwert für den ersten Server ist beispielsweise fe0101.contoso.com und die IP-Adresse 192.168.21.122.

3. Geben fe0.contoso.com in **den Front-End-Server-FQDN** ein, geben Sie 192.168.21.131 in **die Front-End-Server-IP-Adresse ein,** und klicken Sie dann auf **OK**.

4. Das Feature für automatisches Erhöhen aktualisiert alle Server im Pool auf fe01 bis fe06 und alle IP-Adressen von 192.168.21.131 auf 136.

Nachdem Sie alle Bearbeitungen abgeschlossen haben, speichern Sie die Topologie, indem Sie die folgenden Schritte ausführen:

Klicken Sie zum Speichern des Entwurfs des Planungstools auf **Datei** und dann auf **Topologie** speichern oder **Topologie speichern unter**. Wenn ein Dialogfeld **Planungstool speichern unter** angezeigt wird, geben Sie in **Dateiname** einen Namen für die Datei ein, und klicken Sie dann auf **Speichern**.

## <a name="see-also"></a>Siehe auch
<a name="Edit_Network_diagram"> </a>

[Bearbeiten des Entwurfs](/previous-versions/office/lync-server-2013/lync-server-2013-editing-the-design)
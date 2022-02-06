---
title: Bearbeiten der Topologie in Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: 'Nach Abschluss der anfänglichen Fragen können Sie den vollqualifizierten Domänennamen (FQDN) und die IP-Adressen für die Website bearbeiten. Doppelklicken Sie hierzu auf der Seite Globale Topologie auf den Standort, den Sie bearbeiten möchten.'
---

# <a name="edit-the-topology-in-skype-for-business-server-2015"></a>Bearbeiten der Topologie in Skype for Business Server 2015

Nach Abschluss der anfänglichen Fragen können Sie den vollqualifizierten Domänennamen (FQDN) und die IP-Adressen für die Website bearbeiten. Doppelklicken Sie hierzu auf der Seite **Globale Topologie** auf den Standort, den Sie bearbeiten möchten.

Das Planungstool zeigt die Standorttopologie für den ausgewählten Standort an. Im unteren Bereich der Seite für den Standort werden vier Registerkarten angezeigt:

![Standorttopologie des Planungstools.](../../media/Planning_Tool_Site_Topology.png)

- Standorttopologie – Die aktuell angezeigte Seite mit einer visuellen Übersicht über die Topologie, wie empfohlen.

- Edge-Netzwerkdiagramm – Auf der Seite "Edge-Netzwerkdiagramm" übernimmt der Designer die meiste Arbeit im Planungstool. Das Diagramm zeigt die Netzwerkkonfiguration für eine empfohlene Skype for Business Server 2015-Topologie mit bearbeitbaren Einträgen für IP-Adressen und FQDNs für Server, Pool und Hardware und DNS-Lastenausgleich (Domain Name System).

- Edge-Administratorbericht – Der Edge-Administratorbericht enthält insgesamt vier Berichte:

     ![Seite "Edge-Administratorbericht".](../../media/Planning_Tool_Summary_Report.png)

  - Zusammenfassungsbericht – Ein allgemeiner Bericht mit Einstellungen für die Edgenetzwerkkonfiguration. Wenn Sie die Werte auf der Seite " **Edge-Netzwerkdiagramm"** auf die Tcp/IP- und FQDN-Werte der Topologie bearbeiten, die in der tatsächlichen Bereitstellung verwendet werden, werden diese Adressen und Namen hier dargestellt. Andernfalls wird der Standardtext angezeigt.

  - Zertifikatbericht : Der Zertifikatbericht listet den Antragstellernamen und alternative Antragstellernamen für die Zertifikate auf, die für die Topologie erforderlich sind.

  - Firewallbericht: Der Firewallbericht enthält Informationen, die zum Konfigurieren von Umkreisfirewalls in der Infrastruktur erforderlich sind. Dazu gehören die IP-Adressen (standard- oder bearbeitete Werte), Serverrolle, Quell-IP und -Port, Ziel-IP und -Port, Transportprotokoll, Anwendungsprotokoll und relevante Hinweise.

  - DNS-Bericht : Der DNS-Bericht listet relevante Informationen für die DNS-Einträge auf, die Sie erstellen müssen. Hierzu zählen Eintragstyp, FQDN, IP-Adresse und Hinweise zum ordnungsgemäßen Betrieb.

- Websitezusammenfassung – Die Websitezusammenfassung bietet eine Übersicht über die Auswahl, die Sie getroffen haben, indem Sie entweder die anfänglichen Fragen beantworten oder die Werte in **"Designwebsites**" ausfüllen. Außerdem werden Kapazitätsinformationen angezeigt.

    > [!NOTE]
    > Die Informationen auf der Seite mit der Standortzusammenfassung sind auf den jeweiligen Entwurf zugeschnitten und enthält möglicherweise nicht alle Abschnitte oder Informationen, die hier besprochen werden.

## <a name="edit-the-network-configuration-diagram"></a>Bearbeiten des Netzwerkkonfigurationsdiagramms
<a name="Edit_Network_diagram"> </a>

Der Großteil der Arbeit, die ein Designer im Skype for Business Server 2015-Planungstool ausführt, besteht darin, die Einträge für die IP-Adressen und vollqualifizierten Domänennamen (Fully Qualified Domain Names, FQDNs) für die Einträge im Netzwerkdiagramm zu definieren. Die informationen, die auf dieser Seite eingegeben werden, werden in die Berichte und andere Informationen im Planungstool übernommen.

![Planungstools-Netzwerkdiagramm.](../../media/Planning_Tool_Network_Diagram.png)

Das Planungstool erstellt ein Netzwerkdiagramm mit Standardtext für IP-Adressen und FQDNs.

So bearbeiten Sie das Netzwerkdiagramm und geben Werte ein

1. Wählen Sie einen Abschnitt des Netzwerks aus, den Sie bearbeiten möchten. Doppelklicken Sie beispielsweise auf den Text, **access1.contoso.com**. Geben Sie in das daraufhin geöffnete Dialogfeld den tatsächlichen FQDN des Servers access1.contoso.com und die tatsächliche IP-Adresse ein, wobei 131.107.155.3 ersetzt wird.

2. Klicken Sie auf **OK**, um die Einträge zu speichern.

3. Fahren Sie mit der Bearbeitung von IP-Adressen und FQDNs fort, und geben Sie virtuelle IP-Adressen für Hardwaregeräte zum Lastenausgleich oder Servereinträge für einen DNS-Lastenausgleich (Domain Name System) für Server in Pools an.

Eine nützliche Funktion des Planungstools ist die, dass ein Bereich von IP-Adressen und Serverhostnamen inkrementell zugewiesen werden kann. Auf diese Weise muss der für den Entwurf verantwortliche Benutzer die Server in einem Pool nicht einzeln bearbeiten. Beispiel:

1. Doppelklicken Sie auf die Front-End-Server im Pool. Wählen Sie im nun geöffneten Dialogfeld die Option **Möchten Sie IP-Adressen und FQDN als Startpunkte für alle äquivalenten Server im Cluster verwenden?**.

2. Beispielsweise ist der Startwert für den ersten Server fe0101.contoso.com und die IP-Adresse 192.168.21.122.

3. Geben Sie fe0.contoso.com im **Front-End-Server-FQDN** ein, geben Sie 192.168.21.131 in die **IP-Adresse des Front-End-Servers** ein, und klicken Sie dann auf **"OK**".

4. Das Feature für automatisches Erhöhen aktualisiert alle Server im Pool auf fe01 bis fe06 und alle IP-Adressen von 192.168.21.131 auf 136.

Nachdem Sie alle Bearbeitungen abgeschlossen haben, speichern Sie die Topologie, indem Sie die folgenden Schritte ausführen:

Klicken Sie zum Speichern des Entwurfs des Planungstools auf **"Datei**" und dann auf " **Topologie speichern** " oder " **Topologie speichern unter"**. Wenn ein Dialogfeld **Planungstool speichern unter** angezeigt wird, geben Sie in **Dateiname** einen Namen für die Datei ein, und klicken Sie dann auf **Speichern**.

## <a name="see-also"></a>Siehe auch
<a name="Edit_Network_diagram"> </a>

[Bearbeiten des Entwurfs](/previous-versions/office/lync-server-2013/lync-server-2013-editing-the-design)
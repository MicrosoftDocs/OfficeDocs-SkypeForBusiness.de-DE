---
title: Bearbeiten der Topologie in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Nach Beantwortung der anfänglichen Fragen können Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) und die IP-Adressen der Website bearbeiten. Machen Sie hierzu auf der Seite Globale Topologie einen Doppelklick auf den Standort, den Sie bearbeiten möchten.
ms.openlocfilehash: dae99620f34b832dd4abe0baf83d6df11b388750
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816444"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a>Bearbeiten der Topologie in Skype for Business Server 2015

Nach Beantwortung der anfänglichen Fragen können Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) und die IP-Adressen der Website bearbeiten. Machen Sie hierzu auf der Seite **Globale Topologie** einen Doppelklick auf den Standort, den Sie bearbeiten möchten.

Das Planungs Tool zeigt die Standorttopologie für die ausgewählte Website an. Im unteren Bereich der Seite für den Standort werden vier Registerkarten angezeigt:

![Standorttopologie des Planungstools](../../media/Planning_Tool_Site_Topology.png)

- Website Topologie – die aktuell angezeigte Seite mit einer visuellen Übersicht über die Topologie, wie empfohlen.

- Edge-Netzwerkdiagramm – auf der Seite "Edge-Netzwerkdiagramm" werden die meisten Arbeiten des Designers im Planungs Tool ausgeführt. Das Diagramm zeigt die Netzwerkkonfiguration einer empfohlenen Skype for Business Server 2015-Topologie mit bearbeitbaren Einträgen für IP-Adressen und FQDNs für Server, Pool sowie Hardware-und DNS-Lastenausgleichssysteme (Domain Name System) an.

- Edge-Administrator Bericht – der Bericht Edge-Administrator enthält insgesamt vier Berichte:

     ![Seite "Edge-Administrator Bericht"](../../media/Planning_Tool_Summary_Report.png)

  - Zusammenfassungsbericht – ein allgemeiner Bericht über die Einstellungen für die Edge-Netzwerkkonfiguration. Wenn Sie auf der Seite **Edge-Netzwerkdiagramm** die TCP-IP- und FQDN-Werte der Topologie in die der tatsächlichen Bereitstellung ändern, werden diese Adressen und Namen hier dargestellt. Andernfalls wird hier der Standardtext angezeigt.

  - Zertifikat Bericht – im Zertifikat Bericht werden der Antragstellername und die alternativen Namen für die Zertifikate aufgelistet, die für die Topologie erforderlich sind.

  - Firewallbericht – der firewallbericht enthält Informationen, die für die Konfiguration von Umkreisfirewalls in der Infrastruktur erforderlich sind. Diese umfassen die IP-Adressen (entweder die Standardwerte oder die bearbeiteten Werte), Serverrolle, Quell-IP und Port, Ziel-IP und Port, Transportprotokoll, Anwendungsprotokoll und relevante Hinweise.

  - DNS-Bericht – im DNS-Bericht sind relevante Informationen zu den DNS-Einträgen aufgeführt, die Sie erstellen müssen. Hierzu zählen Eintragstyp, FQDN, IP-Adresse und Hinweise zum ordnungsgemäßen Betrieb.

- Website Zusammenfassung: die Website Zusammenfassung zeigt eine Übersicht über die von Ihnen vorgenommenen Auswahlen, indem Sie entweder die ersten Fragen des Interviews beantwortet oder die Werte in **Design Websites**ausgefüllt haben. Es werden auch Kapazitätsinformationen angezeigt.

    > [!NOTE]
    > Die Informationen auf der Seite mit der Standortzusammenfassung sind auf den jeweiligen Entwurf zugeschnitten und enthält möglicherweise nicht alle Abschnitte oder Informationen, die hier besprochen werden.

## <a name="edit-the-network-configuration-diagram"></a>Bearbeiten des Netzwerkkonfigurationsdiagramms
<a name="Edit_Network_diagram"> </a>

Der größte Teil der Arbeit, die ein Designer im Planungs Tool von Skype for Business Server 2015 durchführt, besteht darin, die Einträge für die IP-Adressen und vollqualifizierten Domänennamen (FQDNs) für die Einträge im Netzplandiagramm zu definieren. Die Informationen, die auf dieser Seite eingegeben werden, werden in die Berichte und andere Informationen übernommen, die im Planungs Tool enthalten sind.

![Planungs Tool-Netzwerkdiagramm](../../media/Planning_Tool_Network_Diagram.png)

Das Planungs Tool erstellt ein Netzwerkdiagramm mit Standardtext für IP-Adressen und FQDNs.

So bearbeiten Sie das Netzwerkdiagramm und geben Werte ein

1. Wählen Sie einen Abschnitt des Netzwerks aus, den Sie zuerst bearbeiten möchten. Machen Sie z. B. einen Doppelklick auf den Text **access1.contoso.net**. Geben Sie im nun geöffneten Dialogfeld den tatsächlichen FQDN für den Server „access1.contoso.net“ ein und ersetzen Sie die IP-Adresse 131.107.155.3 durch die tatsächliche IP-Adresse.

2. Klicken Sie auf **OK**, um die Einträge zu speichern.

3. Fahren Sie mit der Bearbeitung von IP-Adressen und FQDNs fort, und geben Sie virtuelle IP-Adressen für Hardwaregeräte zum Lastenausgleich oder Servereinträge für einen DNS-Lastenausgleich (Domain Name System) für Server in Pools an.

Eine nützliche Funktion des Planungstools ist die, dass ein Bereich von IP-Adressen und Serverhostnamen inkrementell zugewiesen werden kann. Auf diese Weise muss der für den Entwurf verantwortliche Benutzer die Server in einem Pool nicht einzeln bearbeiten. Beispiel:

1. Machen Sie einen Doppelklick auf die Front-End-Server im Pool. Wählen Sie im nun geöffneten Dialogfeld die Option **Möchten Sie IP-Adressen und FQDN als Startpunkte für alle äquivalenten Server im Cluster verwenden?**.

2. Beispielsweise lautet der Startwert für den ersten Server "fe0101.contoso.net", und die IP-Adresse ist auf "192.168.21.222" festgelegt.

3. Geben Sie in FQDN des Front-End-Servers den Wert **fe0.contoso.com** und in **IP-Adresse des Front-End-Servers** die Adresse 192.168.21.131 ein und klicken Sie anschließend auf **OK**.

4. Die Funktion zur automatischen inkrementellen Erhöhung aktualisiert alle Server im Pool von "fe01" bis "fe06" und alle IP-Adressen von 192.168.21.131 bis 136.

Nachdem Sie die Bearbeitung abgeschlossen haben, speichern Sie die Topologie, indem Sie folgende Schritte ausführen:

Wenn Sie das Planungs Tool Design speichern möchten, klicken Sie auf **Datei**, und klicken Sie dann auf **Topologie speichern** oder **Topologie speichern**unter. Falls ein Dialogfeld **Planungstool speichern unter** angezeigt wird, geben Sie in **Dateiname** einen Namen für die Datei ein und klicken Sie auf **Speichern**.

## <a name="see-also"></a>Siehe auch
<a name="Edit_Network_diagram"> </a>

[Editing the Design](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)

---
title: Bereitstellen des Pilotpools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Eine der ersten Schritte für die Migration zu Skype für Business Server 2019 erforderlich ist einen pilot Pool bereitstellen. Der pilot Pool ist, in dem Sie Ihre Bereitstellung der Vorversion Koexistenz von Skype für Business Server 2019 testen. Die Koexistenz stellt einen temporären Zustand, der dauert, bis Sie alle Benutzer und Pools zu Skype für Business Server 2019 verschoben haben.
ms.openlocfilehash: e0ac949b0cc7a52e1da5edd9f150e5f59717c08f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890655"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Skype für Business Server 2019 pilot Pool bereitstellen

Eine der ersten Schritte für die Migration zu Skype für Business Server 2019 erforderlich ist einen pilot Pool bereitstellen. Der pilot Pool ist, in dem Sie Ihre Bereitstellung der Vorversion Koexistenz von Skype für Business Server 2019 testen. Die Koexistenz stellt einen temporären Zustand, der dauert, bis Sie alle Benutzer und Pools zu Skype für Business Server 2019 verschoben haben. 
  
Wenn Sie einen pilot Pool bereitstellen, verwenden Sie den definieren neuen Front-End-Pool-Assistenten. Sie sollten die gleichen Merkmale und Arbeitslasten in Ihrer Skype für Business Server 2019 pilot Pool bereitstellen, die Ihnen im vorversionspool. Wenn Sie Archivierungsserver, Monitoring Server und System Center Operations Manager für Archivierung oder Überwachung der vorgängerumgebung bereitgestellt und Archivierung oder Überwachung während der Migrations fortgesetzt werden soll, müssen Sie auch diese Features in Bereitstellen Ihrer Pilot-Umgebung. Die Version, die Sie zur Archivierung oder Überwachung Ihrer Legacy bereitgestellt Umgebung erfasst die Daten in Ihrer Skype für Business Server 2019 Umgebung nicht. 
  
> [!NOTE]
> Das folgende Verfahren beschreibt Features und Einstellungen, die Sie als Teil des Bereitstellungsprozesses insgesamt pilotpool berücksichtigen sollten. In diesem Abschnitt werden nur die wichtigsten Punkte, die Sie als Teil Ihrer Bereitstellung eines pilotpools berücksichtigen sollten. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Zum Bereitstellen einer Skype für Business Server 2019 pilot pool

1. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
2. Erweitern Sie die Struktur bis hinunter zu **Skype für Business Server 2019** > **Enterprise Edition-Front-End-Pools**.
    
3. Mit der rechten Maustaste **Enterprise Edition-Front-End-Pools** , und wählen Sie **Neuen Front-End-Pool**aus.
  
4. Geben Sie den vollqualifizierten Domänennamen (FQDN) von Pools. Wenn Sie dem pilotpool definieren, können Sie einen Enterprise Edition-Front-End-Pool oder Standard Edition-Server bereitstellen. Skype für Business Server 2019 erfordert nicht, dass Ihre pilot Pool-Funktionen übereinstimmen, was im vorversionspool bereitgestellt wurde.
    
    > [!CAUTION]
    > Der Pool oder Server-FQDN, die Sie für den pilotpool definieren muss eindeutig sein. Es kann nicht den Namen des aktuell bereitgestellten vorversionspool oder andere aktuell bereitgestellten Server übereinstimmen. 
  
5. Wählen Sie auf der Seite **Features auswählen** die Kontrollkästchen für die Features, die auf diesem Front-End-Pool aus. Beispielsweise wenn Sie Sofortnachrichten (IM) und Anwesenheitsfeatures bereitgestellt werden, würden Sie das Kontrollkästchen der Konferenzen mit mehreren Teilnehmern Sofortnachrichten zulassen auswählen, aber wählen Sie nicht die einwahlkonferenzen (PSTN) geleitet, Enterprise-VoIP oder Call Admission Control überprüfen Felder, da sie Sprach-, Video- und Zusammenarbeit Konferenzfunktionen darstellen. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. Klicken Sie auf der Seite **verbundene Serverrollen auswählen** wird empfohlen, dass Sie auswählen, den der Vermittlungsserver in Skype für Business Server 2019 zusammenzustellen. Beim Zusammenführen von einer Vorversion Topologie mit Skype für Business Server 2019 müssen Sie zuerst die legacy Mediation Server verbinden. Nach dem Zusammenführen der Topologien und die Skype für Business Server 2019 Mediation Server konfigurieren, können Sie entscheiden, ob der verbundenen Vermittlungsserver beibehalten oder zu einem eigenständigen Server ändern, wenn Sie den Vermittlungsserver in Skype für Business Server verschieben 2019 weiter unten in den Bereitstellungsprozess. 
   
7. Klicken Sie auf der Seite **Serverrollen mit diesem Front-End-Pool zuordnen** Option während der Bereitstellung eines pilotpools, *jedoch nicht* die **aktivieren ein Edge-Pools von der Komponente Media, der diesem Front-End-Pool verwendet werden** . Dies ist ein Feature, die Sie aktivieren und in einer späteren Phase der Migration online schalten. Lassen Sie diese Einstellung deaktiviert für jetzt. 
  
8. Klicken Sie auf **neu**, und geben Sie den FQDN des Anwendungsservers, auf der Seite **Wählen Sie einen Office Web Apps Server** .
  
9. Wählen Sie auf der Seite **die Archivierung von SQL Server-Speicher definieren** , beim Definieren des SQL Server-Speichers für beide Skype für Business-Archivierung und Überwachung für Skype für Business Server 2019 zuvor erstellte SQL Server-Instanz ein. 
  
10. Klicken Sie zum Veröffentlichen Ihrer Topologie Maustaste auf den Knoten **Skype für Business Server** , und klicken Sie dann auf **Topologie veröffentlichen**.
  
11. Wenn der Veröffentlichungsvorgang abgeschlossen ist, klicken Sie auf **Fertig stellen**.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  


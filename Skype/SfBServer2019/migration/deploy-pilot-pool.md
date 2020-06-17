---
title: Bereitstellen des Pilotpools
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Einer der ersten Schritte, die für die Migration zu Skype for Business Server 2019 erforderlich sind, ist die Bereitstellungeines pilotpools. Der Pilot Pool testet die Koexistenz von Skype for Business Server 2019 mit Ihrer Legacy-Bereitstellung. Koexistenz ist ein temporärer Zustand, der dauert, bis Sie alle Benutzer und Pools in Skype for Business Server 2019 verschoben haben.
ms.openlocfilehash: 46d8b6fd6cefa2894f67a1c24732ace01ca65785
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752857"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Bereitstellen des pilotpools für Skype for Business Server 2019

Einer der ersten Schritte, die für die Migration zu Skype for Business Server 2019 erforderlich sind, ist die Bereitstellungeines pilotpools. Der Pilot Pool testet die Koexistenz von Skype for Business Server 2019 mit Ihrer Legacy-Bereitstellung. Koexistenz ist ein temporärer Zustand, der dauert, bis Sie alle Benutzer und Pools in Skype for Business Server 2019 verschoben haben. 
  
Beim Bereitstellen eines Pilotpools verwenden Sie den Assistenten zum Definieren eines neuen Front-End-Pools. Sie sollten dieselben Funktionen und Arbeitslasten in Ihrem Skype for Business Server 2019-Pilot Pool bereitstellen, den Sie in Ihrem Legacy Pool haben. Wenn Sie Archivierungsserver, Monitoring Server oder System Center Operations Manager zur Archivierung oder Überwachung ihrer Vorgänger Umgebung bereitgestellt haben und die Archivierung oder Überwachung während der Migration fortsetzen möchten, müssen Sie diese Features auch in ihrer Pilotumgebung bereitstellen. Die Version, die Sie zum Archivieren oder überwachen ihrer Vorgänger Umgebung bereitgestellt haben, erfasst keine Daten in Ihrer Skype for Business Server 2019-Umgebung. 
  
> [!NOTE]
> In den nachfolgenden Verfahren werden Features und Einstellungen behandelt, die Sie im Rahmen des allgemeinen Bereitstellungsprozesses für Pilotpools berücksichtigen sollten. In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotpools hervorgehoben. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>So stellen Sie einen Skype for Business Server 2019-Pilot Pool bereit

1. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
2. Erweitern Sie die Struktur, bis Sie **Skype for Business Server 2019**  >  **Enterprise Edition-Front-End-Pools**erreichen.
    
3. Klicken Sie mit der rechten Maustaste auf **Enterprise Edition-Front-End-Pools** , und wählen Sie **neuer Front-End**
  
4. Geben Sie den vollqualifizierten Domänennamen (FQDN) des Pools ein. Wenn Sie Ihren Pilot Pool definieren, können Sie eine Enterprise Edition-Front-End-Pool oder ein Standard Edition-Server bereitstellen. Für Skype for Business Server 2019 ist es nicht erforderlich, dass die Pilot Pool Features mit dem übereinstimmen, was in Ihrem Legacy Pool bereitgestellt wurde.
    
    > [!CAUTION]
    > Der Pool oder Server-FQDN, den Sie für den Pilot-Pool definieren, muss eindeutig sein. Er kann nicht mit dem Namen des derzeit bereitgestellten Legacy Pools oder aller derzeit bereitgestellten Server übereinstimmen. 
  
5. Aktivieren Sie auf der Seite **Features auswählen** die Kontrollkästchen für die Features, die in diesem Front-End-Pool werden sollen. Wenn Sie beispielsweise nur Instant Messaging-und Anwesenheitsfunktionen bereitstellen, aktivieren Sie das Kontrollkästchen Konferenzen, um mehr Parteien-Chat zu ermöglichen, aber Sie können nicht die Kontrollkästchen für Einwahlkonferenzen, Enterprise-VoIP oder Anrufsteuerung auswählen, da Sie die Features für VoIP-, Video-und Konferenz Konferenzen darstellen. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. Auf der Seite **"verbundene Serverrollen auswählen** " wird empfohlen, die Vermittlungsserver in Skype for Business Server 2019 collocate. Wenn Sie eine Legacy Topologie mit Skype for Business Server 2019 zusammenführen, müssen Sie zuerst die Legacy Vermittlungsserver collocate. Nachdem Sie die Topologien zusammengeführt und die Skype for Business Server 2019 Vermittlungsserver konfiguriert haben, können Sie entscheiden, ob Sie die verbundenen Vermittlungsserver beibehalten oder Sie in einen eigenständigen Server ändern möchten, wenn Sie die Vermittlungsserver Rolle später im Bereitstellungsprozess auf Skype for Business Server 2019 umstellen. 
   
7. Wählen Sie auf der Seite **Serverrollen mit dieser Front-End-Pool zuordnen** während der Bereitstellungeines pilotpools *nicht* die Option **Edgepool von der medienkomponente dieser Front-End-Pool aktivieren** aus. Diese Funktion wird in einer späteren Phase der Migration aktiviert und online geschaltet. Lassen Sie diese Einstellung zu diesem Zeitpunkt deaktiviert. 
  
8. Klicken Sie auf der Seite **Einen Office Web Apps-Server auswählen** auf **Neu**, und geben Sie den FQDN des Anwendungsservers an.
  
9. Wählen Sie auf der Seite **Archivierungs SQL Server Speicher definieren** beim Definieren des SQL Server Speichers sowohl für Skype for Business Server Archivierung als auch für die Überwachung die zuvor für Skype for Business Server 2019 erstellte SQL Server Instanz aus. 
  
10. Klicken Sie zum Veröffentlichen der Topologie mit der rechten Maustaste auf den Knoten **Skype for Business Server** , und klicken Sie dann auf **Topologie veröffentlichen**.
  
11. Klicken Sie nach Abschluss der Veröffentlichung auf **Fertig stellen**.

12. Bevor Sie zum nächsten Abschnitt mit dem Namen "Überprüfen der Koexistenz von pilotpools mit Legacy Pool" wechseln, müssen Sie den Skype for Business Server neuen Front-End-Pilot Pool installieren, den wir soeben in der veröffentlichten Topologie definiert haben, und führen Sie die hier beschriebenen Schritte aus, um [Skype for Business Server auf Servern in der Topologie zu installieren](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server) .

13. Wenn der vorherige Schritt abgeschlossen ist, fahren Sie mit dem nächsten Abschnitt fort, um die Koexistenz des pilotpools mit dem Legacy Pool zu überprüfen.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  


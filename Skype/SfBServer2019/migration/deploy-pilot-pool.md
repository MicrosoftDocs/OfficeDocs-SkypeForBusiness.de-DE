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
description: Einer der ersten erforderlichen Schritte für die Migration zu Skype for Business Server 2019 ist die Bereitstellung eines Pilotpools. Im Pilotpool testen Sie die Koexistenz von Skype for Business Server 2019 mit Ihrer Legacybereitstellung. Koexistenz ist ein temporärer Zustand, der bis zum Wechsel aller Benutzer und Pools zu Skype for Business Server 2019 dauert.
ms.openlocfilehash: a8d9a1bbe5f629a91721ebe530e6a192e3e65b62
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113291"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Bereitstellen des Skype for Business Server 2019-Pilotpools

Einer der ersten erforderlichen Schritte für die Migration zu Skype for Business Server 2019 ist die Bereitstellung eines Pilotpools. Im Pilotpool testen Sie die Koexistenz von Skype for Business Server 2019 mit Ihrer Legacybereitstellung. Koexistenz ist ein temporärer Zustand, der bis zum Wechsel aller Benutzer und Pools zu Skype for Business Server 2019 dauert. 
  
Beim Bereitstellen eines Pilotpools verwenden Sie den Assistenten zum Definieren eines neuen Front-End-Pools. Sie sollten die gleichen Features und Arbeitsauslastungen in Ihrem Skype for Business Server 2019-Pilotpool bereitstellen, die Sie im Legacypool haben. Wenn Sie Archivierungsserver, Monitoring Server oder System Center Operations Manager für die Archivierung oder Überwachung Ihrer Legacyumgebung bereitgestellt haben und die Archivierung oder Überwachung während der gesamten Migration fortsetzen möchten, müssen Sie diese Features auch in Ihrer Pilotumgebung bereitstellen. Die Version, die Sie zum Archivieren oder Überwachen Ihrer Legacyumgebung bereitgestellt haben, erfasst keine Daten in Ihrer Skype for Business Server 2019-Umgebung. 
  
> [!NOTE]
> In den nachfolgenden Verfahren werden Features und Einstellungen behandelt, die Sie im Rahmen des allgemeinen Bereitstellungsprozesses für Pilotpools berücksichtigen sollten. In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotpools hervorgehoben. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>So stellen Sie einen Skype for Business Server 2019-Pilotpool zur Verfügung

1. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
2. Erweitern Sie die Struktur, bis **Sie Skype for Business Server 2019** Enterprise Edition  >  **Front-End-Pools erreichen.**
    
3. Klicken Sie mit der rechten Maustaste **auf Enterprise Edition Front-End-Pools,** und wählen **Sie Neuen Front-End-Pool aus.**
  
4. Geben Sie den vollqualifizierten Domänennamen (FQDN) des Pools ein. Wenn Sie den Pilotpool definieren, können Sie einen Enterprise Edition-Front-End-Pool oder einen Standard Edition-Server bereitstellen. Skype for Business Server 2019 erfordert nicht, dass die Pilotpoolfeatures mit den features übereinstimmen, die in Ihrem Legacypool bereitgestellt wurden.
    
    > [!CAUTION]
    > Der FQDN des Pools oder Servers, den Sie für den Pilotpool definieren, muss eindeutig sein. Er kann nicht mit dem Namen des aktuell bereitgestellten Legacypools oder anderen derzeit bereitgestellten Servern übereinstimmen. 
  
5. Aktivieren Sie **auf der** Seite Features auswählen die Kontrollkästchen für die Features, die Sie in diesem Front-End-Pool wünschen. Wenn Sie beispielsweise nur Chat- und Anwesenheitsfeatures bereitstellen, aktivieren Sie das Kontrollkästchen Konferenzkonferenz, um Chatnachrichten mit mehrerenPartys zu ermöglichen. Sie würden jedoch nicht die Kontrollkästchen Einwahlkonferenz, Enterprise-VoIP oder Anrufsteuerung aktivieren, da sie Sprach-, Video- und kollaborative Konferenzfunktionen darstellen. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. Auf der Seite Mit **Serverrollen** auswählen wird empfohlen, den Vermittlungsserver in Skype for Business Server 2019 zu verbinden. Wenn Sie eine ältere Topologie mit Skype for Business Server 2019 zusammenführen, müssen Sie zuerst den Legacyvermittlungsserver verbinden. Nach dem Zusammenführen der Topologien und dem Konfigurieren des Skype for Business Server 2019-Vermittlungsservers können Sie entscheiden, ob der zusammengeführte Vermittlungsserver erhalten bleiben soll, oder ihn in einen eigenständigen Server ändern, wenn Sie die Vermittlungsserverrolle später im Bereitstellungsprozess auf Skype for Business Server 2019 verschieben. 
   
7. Wählen Sie auf der Seite Serverrollen diesem **Front-End-Pool** zuordnen während der Pilotpoolbereitstellung nicht die Option Edgepool aktivieren, die von der Medienkomponente dieses  **Front-End-Pools verwendet** werden soll. Diese Funktion wird in einer späteren Phase der Migration aktiviert und online geschaltet. Lassen Sie diese Einstellung zu diesem Zeitpunkt deaktiviert. 
  
8. Klicken Sie auf der Seite **Einen Office Web Apps-Server auswählen** auf **Neu**, und geben Sie den FQDN des Anwendungsservers an.
  
9. Wählen Sie auf der Seite Archivierung **SQL Server-Speicher** definieren beim Definieren des SQL Server-Speichers für die Archivierung und Überwachung von Skype for Business Server die zuvor für Skype for Business Server 2019 erstellte SQL Server-Instanz aus. 
  
10. Klicken Sie zum Veröffentlichen Ihrer Topologie mit der rechten Maustaste auf den **Knoten Skype for Business Server,** und klicken Sie dann auf **Topologie veröffentlichen.**
  
11. Klicken Sie nach Abschluss der Veröffentlichung auf **Fertig stellen**.

12. Bevor Sie zum nächsten Abschnitt mit dem Namen "Überprüfen der Koexistenz des Pilotpools mit dem Legacypool" umgeschaltet werden, müssen Sie den neuen Front-End-Pilotpool von Skype for Business Server installieren, den wir gerade in der veröffentlichten Topologie definiert haben. Befolgen Sie die hier beschriebenen Verfahren Installieren von Skype for Business Server auf Servern in der [Topologie.](../../SfbServer/deploy/install/install-skype-for-business-server.md)

13. Wenn der vorherige Schritt abgeschlossen ist, wechseln Sie zum nächsten Abschnitt, um die Koexistenz des Pilotpools mit dem Legacypool zu überprüfen.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->

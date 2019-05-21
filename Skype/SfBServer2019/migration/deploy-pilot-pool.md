---
title: Bereitstellen des Pilotpools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Einer der ersten Schritte, die für die Migration zu Skype for Business Server 2019 erforderlich sind, ist die Bereitstellungeines pilotpools. Im Pilot Pool testen Sie die Koexistenz von Skype for Business Server 2019 mit Ihrer Legacy Bereitstellung. Koexistenz ist ein vorübergehender Zustand, der dauert, bis Sie alle Benutzer und Pools in Skype for Business Server 2019 verschoben haben.
ms.openlocfilehash: 3642d603b5923a554b8eca41a948125ef25526ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280864"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Bereitstellen des pilotpools für Skype for Business Server 2019

Einer der ersten Schritte, die für die Migration zu Skype for Business Server 2019 erforderlich sind, ist die Bereitstellungeines pilotpools. Im Pilot Pool testen Sie die Koexistenz von Skype for Business Server 2019 mit Ihrer Legacy Bereitstellung. Koexistenz ist ein vorübergehender Zustand, der dauert, bis Sie alle Benutzer und Pools in Skype for Business Server 2019 verschoben haben. 
  
Wenn Sie einen Pilot Pool bereitstellen, verwenden Sie den Assistenten zum Definieren eines neuen Front-End-Pools. Sie sollten dieselben Features und Arbeitsauslastungen in Ihrem Skype for Business Server 2019-Pilot Pool bereitstellen, den Sie in Ihrem Legacy Pool haben. Wenn Sie den Archivierungsserver, den Monitoring Server oder den System Center Operations Manager zum Archivieren oder Überwachen Ihrer Legacyumgebung bereitgestellt haben und die Archivierung oder Überwachung während der gesamten Migration fortsetzen möchten, müssen Sie diese Features auch in Ihrem Pilotumgebung. Die Version, die Sie zum Archivieren oder Überwachen Ihrer Legacyumgebung bereitgestellt haben, erfasst keine Daten in Ihrer Skype for Business Server 2019-Umgebung. 
  
> [!NOTE]
> Im folgenden Verfahren werden die Features und Einstellungen erörtert, die Sie im Rahmen des gesamten Bereitstellungsprozesses für pilotpools berücksichtigen sollten. In diesem Abschnitt werden nur wichtige Punkte hervorgehoben, die Sie im Rahmen der Bereitstellung des pilotpools berücksichtigen sollten. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>So stellen Sie einen Skype for Business Server 2019-Pilot Pool bereit

1. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
2. Erweitern Sie die Struktur, bis Sie **Skype for Business Server 2019** > **Enterprise Edition-Front-End-Pools**erreichen.
    
3. Klicken Sie mit der rechten Maustaste auf **Enterprise Edition-Front-End-Pools** , und wählen Sie **Neues Front-End**
  
4. Geben Sie den vollqualifizierten Domänennamen (FQDN) des Pools ein. Wenn Sie Ihren Pilot Pool definieren, können Sie auswählen, ob Sie einen Enterprise Edition-Front-End-Pool oder einen Standard Edition-Server bereitstellen möchten. Für Skype for Business Server 2019 ist es nicht erforderlich, dass die Features Ihres pilotpools mit dem übereinstimmen, was in Ihrem Legacy Pool bereitgestellt wurde.
    
    > [!CAUTION]
    > Der Pool-oder Server-FQDN, den Sie für den Pilot Pool definieren, muss eindeutig sein. Sie kann nicht mit dem Namen des aktuell bereitgestellten Legacy Pools oder aller anderen Server übereinstimmen, die derzeit bereitgestellt werden. 
  
5. Aktivieren Sie auf der Seite **Features auswählen** die Kontrollkästchen für die Features, die in diesem Front-End-Pool angezeigt werden sollen. Wenn Sie beispielsweise nur Chat-und Anwesenheitsfeatures bereitstellen, aktivieren Sie das Kontrollkästchen Konferenz Konferenzen, um die mehrteilige Chatfunktion zuzulassen, aber Sie würden die Überprüfung für Einwahlkonferenzen, Enterprise-VoIP oder Anrufsteuerung nicht auswählen. -Felder, da Sie sprach-, Video-und kollaborative Konferenzfeatures darstellen. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. Auf der Seite **"ausgewählte Serverrollen auswählen** " empfehlen wir, den Vermittlungsserver in Skype for Business Server 2019 zu collocate. Wenn Sie eine Legacy Topologie mit Skype for Business Server 2019 zusammenführen, müssen Sie zuerst den Legacy-Vermittlungsserver collocate. Nachdem Sie die Topologien zusammengeführt und den Vermittlungsserver für Skype for Business Server 2019 konfiguriert haben, können Sie entscheiden, ob Sie den beiliegenden Vermittlungsserver beibehalten oder auf einen eigenständigen Server ändern möchten, wenn Sie die Vermittlungsserver Rolle in Skype for Business Server verschieben. 2019. 
   
7. Wählen Sie auf der Seite **Associate Server Roles with this Front End Pool** während der Bereitstellung des pilotpools *nicht* die Option **einen Edge-Pool aktivieren, der von der medienkomponente dieser Front-End-Pool Option verwendet werden soll** . Dies ist ein Feature, das Sie in einer späteren Migrationsphase aktivieren und online schalten können. Lassen Sie diese Einstellung für jetzt deaktiviert. 
  
8. Klicken Sie auf der Seite **Office Web Apps-Server auswählen** auf **neu**, und geben Sie den FQDN des Anwendungsservers an.
  
9. Wählen Sie auf der Seite **Archivierungs-SQL Server-Speicher definieren** beim Definieren des SQL Server-Speichers für Skype for Business Server-Archivierung und-Überwachung die SQL Server-Instanz aus, die zuvor für Skype for Business Server 2019 erstellt wurde. 
  
10. Wenn Sie Ihre Topologie veröffentlichen möchten, klicken Sie mit der rechten Maustaste auf den Knoten **Skype for Business Server** , und klicken Sie dann auf **Topologie veröffentlichen**.
  
11. Wenn der Veröffentlichungsprozess abgeschlossen ist, klicken Sie auf **Fertig stellen**.

12. Bevor Sie zum nächsten Abschnitt "Überprüfen der Koexistenz von pilotpools mit Legacy Pool" wechseln, müssen Sie den neuen Front-End-Pilot Pool von Skype for Business Server installieren, den wir soeben in der veröffentlichten Topologie definiert haben, und folgen Sie den hier beschriebenen Schritten unter [Installieren von Skype für Business Server auf Servern in der Topologie](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)

13. Wenn der vorherige Schritt abgeschlossen ist, wechseln Sie zum nächsten Abschnitt, um die Koexistenz des pilotpools mit dem Legacy Pool zu überprüfen.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  


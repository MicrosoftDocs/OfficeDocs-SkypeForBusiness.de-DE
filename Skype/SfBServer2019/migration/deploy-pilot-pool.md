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
description: Einer der ersten Erforderlichen für die Migration zu Skype for Business Server 2019 ist die Bereitstellung eines Pilotpools. Im Pilotpool testen Sie die Koexistenz von Skype for Business Server 2019 mit Ihrer Legacybereitstellung. Koexistenz ist ein temporärer Zustand, der so lange gilt, bis Sie alle Benutzer und Pools in Skype for Business Server 2019 verschoben haben.
ms.openlocfilehash: d7e02d1cb921f973d8851cfc3c8bbff0f3e81aa92f1945584ee94fa59a45e9ee
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279603"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Bereitstellen Skype for Business Server 2019-Pilotpools

Einer der ersten Erforderlichen für die Migration zu Skype for Business Server 2019 ist die Bereitstellung eines Pilotpools. Im Pilotpool testen Sie die Koexistenz von Skype for Business Server 2019 mit Ihrer Legacybereitstellung. Koexistenz ist ein temporärer Zustand, der so lange gilt, bis Sie alle Benutzer und Pools in Skype for Business Server 2019 verschoben haben. 
  
Beim Bereitstellen eines Pilotpools verwenden Sie den Assistenten zum Definieren eines neuen Front-End-Pools. Sie sollten die gleichen Features und Workloads in Ihrem Skype for Business Server 2019-Pilotpool bereitstellen, den Sie in Ihrem Legacypool haben. Wenn Sie Archivierungsserver, Monitoring Server oder System Center Operations Manager für die Archivierung oder Überwachung Ihrer älteren Umgebung bereitgestellt haben und die Archivierung oder Überwachung während der gesamten Migration fortsetzen möchten, müssen Sie diese Features auch in Ihrer Pilotumgebung bereitstellen. Die Version, die Sie zum Archivieren oder Überwachen Ihrer Legacyumgebung bereitgestellt haben, erfasst keine Daten in Ihrer Skype for Business Server 2019-Umgebung. 
  
> [!NOTE]
> In den nachfolgenden Verfahren werden Features und Einstellungen behandelt, die Sie im Rahmen des allgemeinen Bereitstellungsprozesses für Pilotpools berücksichtigen sollten. In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotpools hervorgehoben. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>So stellen Sie einen Skype for Business Server 2019-Pilotpool bereit

1. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
2. Erweitern Sie die Struktur, bis Sie **Skype for Business Server 2019**  >  **Enterprise Edition Front-End-Pools** erreichen.
    
3. Klicken Sie mit der rechten Maustaste **auf Enterprise Edition Front-End-Pools,** und wählen Sie **"Neuer Front-End-Pool" aus.**
  
4. Geben Sie den vollqualifizierten Domänennamen (FQDN) des Pools ein. Wenn Sie Ihren Pilotpool definieren, können Sie einen Enterprise Edition Front-End-Pool oder einen Standard Edition Server bereitstellen. Skype for Business Server 2019 erfordert nicht, dass ihre Pilotpoolfeatures mit den Funktionen in Ihrem Legacypool übereinstimmen.
    
    > [!CAUTION]
    > Der Pool- oder Server-FQDN, den Sie für den Pilotpool definieren, muss eindeutig sein. Sie kann nicht mit dem Namen des derzeit bereitgestellten Legacypools oder anderer derzeit bereitgestellter Server übereinstimmen. 
  
5. Aktivieren Sie auf der Seite **"Features auswählen"** die Kontrollkästchen für die Features, die in diesem Front-End-Pool angezeigt werden sollen. Wenn Sie z. B. nur Chat- und Anwesenheitsfunktionen bereitstellen, aktivieren Sie das Kontrollkästchen "Konferenzen", um Chatnachrichten mit mehreren Teilnehmern zuzulassen. Sie würden jedoch nicht die Kontrollkästchen für Einwahlkonferenzen (PSTN), Enterprise-VoIP oder Anrufsteuerung aktivieren, da sie VoIP-, Video- und Konferenzfunktionen für die Zusammenarbeit darstellen. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. Auf der Seite **"Gemeinsam zugeordnete Serverrollen auswählen"** wird empfohlen, den Vermittlungsserver in Skype for Business Server 2019 gemeinsam zu verwenden. Beim Zusammenführen einer Legacytopologie mit Skype for Business Server 2019 müssen Sie zuerst den Legacy-Vermittlungsserver verbinden. Nach dem Zusammenführen der Topologien und dem Konfigurieren des Skype for Business Server 2019-Vermittlungsservers können Sie entscheiden, ob der zugeordnete Vermittlungsserver beibehalten oder auf einen eigenständigen Server geändert werden soll, wenn Sie die Vermittlungsserverrolle später im Bereitstellungsprozess auf Skype for Business Server 2019 verschieben. 
   
7. Wählen Sie auf der Seite **"Serverrollen diesem Front-End-Pool zuordnen"** während der Pilotpoolbereitstellung *nicht* den Edgepool aktivieren, **der von der Medienkomponente dieser Front-End-Pooloption verwendet werden soll.** Diese Funktion wird in einer späteren Phase der Migration aktiviert und online geschaltet. Lassen Sie diese Einstellung zu diesem Zeitpunkt deaktiviert. 
  
8. Klicken Sie auf der Seite **Einen Office Web Apps-Server auswählen** auf **Neu**, und geben Sie den FQDN des Anwendungsservers an.
  
9. Wählen Sie auf der Seite **"Archivierung SQL Server Speicher definieren"** beim Definieren des SQL Server Speichers für Skype for Business Server Archivierung und Überwachung die SQL Server Instanz aus, die zuvor für Skype for Business Server 2019 erstellt wurde. 
  
10. Klicken Sie zum Veröffentlichen der Topologie mit der rechten Maustaste auf den **knoten Skype for Business Server,** und klicken Sie dann auf **"Topologie veröffentlichen".**
  
11. Klicken Sie nach Abschluss der Veröffentlichung auf **Fertig stellen**.

12. Bevor Sie zum nächsten Abschnitt namens "Überprüfen der Koexistenz von Pilotpools mit Legacypool" wechseln, müssen Sie den Skype for Business Server neuen Front-End-Pilotpool installieren, den wir gerade in der veröffentlichten Topologie definiert haben. Befolgen Sie die hier beschriebenen Verfahren [installieren Skype for Business Server auf Servern in der Topologie.](../../SfbServer/deploy/install/install-skype-for-business-server.md)

13. Wechseln Sie nach Abschluss des vorherigen Schritts zum nächsten Abschnitt, um die Koexistenz des Pilotpools mit dem Legacypool zu überprüfen.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->

---
title: Front-End-Pool Disaster Recovery in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
description: Skype für Business Server bietet für Disaster Recovery und poolpaaren mit Failover für den Fall, dass ein Pool ausfällt.
ms.openlocfilehash: 9d35ecde963cbee72bb23294f0e5b02dc1477b12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910298"
---
# <a name="front-end-pool-disaster-recovery-in-skype-for-business-server"></a>Front-End-Pool Disaster Recovery in Skype für Business Server
 
Skype für Business Server bietet für Disaster Recovery und poolpaaren mit Failover für den Fall, dass ein Pool ausfällt.
  
Bereitstellen von Paare von Front-End-Pools für die meisten robusten Disaster Recovery Optionen in Skype für Business Server auf zwei geografisch verteilte Standorte. Jeder Standort verfügt über einen Front-End-Pool, für den es einen entsprechenden Front-End-Pool am anderen Standort gibt. Beide Standorte sind aktiv, und der Sicherungsdienst ermöglicht die Datenreplikation in Echtzeit, damit die Pools synchronisiert bleiben. Wenn Sie Front-End-poolpaarung implementieren möchten, finden Sie unter [Deploy gepaart Front-End-Pools für die Wiederherstellung in Skype für Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md) .
  
![Zeigt Front-End-Pools an zwei verschiedenen Standorten, die miteinander gepaart sind](../../media/f74533c0-a10e-4f18-85a8-b9a008497573.jpg)
  
Falls der Pool an einem Standort ausfällt, können Sie für die Benutzer ein Failover von diesem Pool auf den Pool am anderen Standort vornehmen, von dem dann für alle Benutzer in beiden Pools Dienste bereitgestellt werden. Für die Kapazitätsplanung sollte bei einem Notfall jeder Pool in der Lage sein, die Arbeitsauslastung aller Benutzer in beiden Pools zu bewältigen.
  
Zwei Rechenzentren, die die als Paar bereitgestellten Front-End-Pools enthalten, können beliebig weit voneinander entfernt stehen. Wir empfehlen die Verwendung zweier Rechenzentren in derselben Weltregion mit Hochgeschwindigkeitsverbindung. 
  
Die Verwendung zweier Rechenzentren in verschiedenen Weltregionen ist zwar möglich, führt jedoch u. U. zu größeren Datenverlusten aufgrund von Wartezeiten bei der Datenreplikation.
  
Beachten Sie bei der Planung, welche Pools als Paar bereitgestellt werden, dass nur die folgenden Paarungen unterstützt werden:
  
- Enterprise Edition-Pools können nur mit anderen Enterprise Edition-Pools gepaart werden. Entsprechend können Standard Edition-Pools nur mit anderen Standard Edition-Pools gepaart werden.
    
- Physische Pools können nur mit anderen physischen Pools gepaart werden. Entsprechend können virtuelle Pools nur mit anderen virtuellen Pools gepaart werden.
    
- Gepaarte Pools müssen unter demselben grundlegenden Betriebssystem laufen.
    
Eine Paarung zweier Pools, die nicht diesen Empfehlungen entspricht, wird weder durch den Topologie-Generator noch durch die Topologieüberprüfung verhindert. Der Topologie-Generator lässt z. B. die Paarung eines Enterprise Edition-Pools mit einem Standard Edition-Pool zu. Diese Art von Paarung wird jedoch nicht unterstützt.
  
## <a name="backup-registrar-relationships-and-survivable-branch-appliances"></a>Backup Registrierungsstelle Beziehungen und Survivable Branch Appliances

Neben der Notfallwiederherstellung dienen die verbundenen Pools als Sicherungsregistrierungsstellen füreinander. Jeder Pool kann die Sicherung für nur einen anderen Front-End-Pool sein.
  
Auch wenn Beziehungen von Sicherungsregistrierungsstellen zwischen zwei Front-End-Pools 1:1 und symmetrisch sein müssen, kann jeder Front-End-Pool auch eine Sicherungsregistrierung für eine Reihe von Survivable Branch Appliances sein.
  
Beachten Sie, dass Skype for Business die Notfallwiederherstellung für Benutzer auf einer Survivable Branch Appliance unterstützt. Wenn ein Front-End-Pool ausfällt, der als Sicherung für eine Survivable Branch Appliance dient, werden die bei der Survivable Branch Appliance angemeldeten Benutzer in den Ausfallsicherheitsmodus versetzt, selbst nachdem die Benutzer auf dem Front-End-Pool auf den Backup-Front-End-Pool verschoben wurden.
  
## <a name="recovery-time-for-pool-failover-and-pool-failback"></a>Wiederherstellungsdauer bei einem Failover und Failback eines Pools

Bei einem Failover und Failback eines Pools ist das engineering Ziel für Recovery Time Objectives (RTO) 15 bis 20 Minuten. Hierbei handelt es sich um den Zeitaufwand für das Failover ausgeführt, nachdem es Administratoren bestimmt haben, wurde von ein Notfall, und die FailoverVerfahren gestartet. Umfasst nicht die Zeit für Administratoren bei der Bewertung der Situation und treffen einer Entscheidung, und umfasst auch den Zeitpunkt den Benutzer erneut anmelden, nach dem Failover abgeschlossen ist.
  
Für Poolfailover und Poolfailbacks liegt das Entwicklungsziel für das Recovery Time Objective (RTO) bei 5 Minuten. Dies definiert die Zeitspanne, in der Daten aufgrund des Notfalls und aufgrund der Replikationswartezeit des Sicherungsdienstes verloren gehen können. Beispiel: bei ein Pool ausfällt, 10:00 Uhr und RPO ist 5 Minuten, auf den Pool zwischen 9:55 Uhr geschriebene Daten und 10:00 Uhr .might nicht mit dem Sicherungspool repliziert und würde verloren.
  
Alle RTO- und RPO-Nummern in diesem Dokument wird davon ausgegangen, dass die zwei Rechenzentren innerhalb desselben Bereichs World mit Hochgeschwindigkeits, geringer Latenz Transport zwischen den beiden Standorten befinden. Diese Nummern werden für einen Pool mit 40.000 gleichzeitig aktive Benutzer und 200.000 Benutzern im Hinblick auf eine vordefinierte Benutzermodell für Lync aktivierten gemessen in Datenreplikation Backlogs vorhanden ist. Sie werden können basierend auf Leistungstests und Validierung geändert.
  
## <a name="central-management-store-failover"></a>Failover des zentralen Verwaltungsspeichers

Der zentrale Verwaltungsspeicher enthält Konfigurationsdaten zu Servern und Diensten in Ihrer Bereitstellung. Jede Skype für Business Server-Bereitstellung umfasst einen zentralen Verwaltungsspeicher, die vom Back End-Server von einem Front-End-Pool gehostet wird.
  
Wenn ein Paar, Pools, der den zentralen Verwaltungsspeicher einer zentralen Speicher Sicherungsdatenbank hostet ist, im Sicherungspool eingerichtet werden. Zu jedem Zeitpunkt eine der zwei Datenbanken zentralen Speicher aktiv ist, und der andere eine Standby. Der Inhalt wird von den Sicherungsdienst aus der aktiven Datenbank auf dem Standbymodus repliziert.
  
![Zeigt zwei Front-End-Pools, einen mit dem aktiven CMS-Speicher und den anderen mit dem passiven CMS-Sicherungsspeicher](../../media/aa479398-eb56-4854-8d50-1eff39c58a56.jpg)
  
Während eines Poolfailovers, von dem die Pools betroffen sind, die den zentralen Verwaltungsspeicher hosten, müssen Sie den zentralen Verwaltungsspeicher ändern, bevor Sie das Failover für den Front-End-Pool durchführen.
  
Nach der Behebung des Notfalls ist es nicht erforderlich, einen Failback des zentralen Verwaltungsspeichers durchzuführen. Der zentrale Verwaltungsspeicher kann in dem Pool bleiben, zu dem er geändert wurde.
  
Die Entwicklungsziele für den zentralen Verwaltungsspeicher sind 5 Minuten für die Wiederherstellungsdauer (Recovery Time Objective, RTO) und 5 Minuten für den Wiederherstellungspunkt (Recovery Point Objective, RPO).
  
## <a name="front-end-pool-pairing-data-security"></a>Datensicherheit beim Bilden von Front-End-Poolpaaren

Der Sicherungsdienst überträgt kontinuierlich Benutzerdaten und Konferenzinhalte zwischen zwei gepaarten Front-End-Pools. Zu den Benutzerdaten gehören SIP-URIs von Benutzern sowie Konferenzpläne, Kontaktlisten und Einstellungen. Zu Konferenzinhalten gehören hochgeladene Microsoft PowerPoint-Präsentationen sowie in Konferenzen genutzte Whiteboards.
  
Vom Quellpool werden die Daten aus dem lokalen Speicher exportiert, gezippt und zum Zielpool übertragen, wo sie entzippt und in den lokalen Speicher importiert werden. Der Sicherungsdienst geht davon aus, dass die Kommunikationsverbindung zwischen den beiden Rechenzentren innerhalb des Unternehmensnetzwerks besteht, das vor dem Internet geschützt ist. Daher werden die übertragenen Daten nicht zwischen den zwei Rechenzentren verschlüsselt und auch nicht innerhalb eines sicheren Protokolls, etwa HTTPS, nativ verschlüsselt. Aus diesem Grund kann ein Man-in-the-Middle-Angriff von internen Mitarbeiter innerhalb des Unternehmensnetzwerks.
  
Jedes Unternehmen, das Skype für Business Server über mehrere Rechenzentren bereitgestellt und verwendet die Disaster Recovery-Funktion muss sicherstellen, dass Datenverkehr zwischen Rechenzentren durch ihre Unternehmensintranet geschützt ist. Unternehmen, die ihren Datenverkehr vor internen Angriffen schützen möchten, müssen die Kommunikationsverbindungen zwischen den Rechenzentren schützen. Dies ist eine standardmäßige Voraussetzung, die auch viele andere Arten von vertraulichen Unternehmensdaten schützt, die zwischen Rechenzentren übertragen werden.
  
Das Risiko von Man-in-the-Middle-Angriffen innerhalb des Unternehmensnetzwerks besteht zwar, doch ist es im Vergleich zur Gefährdung des Datenverkehrs im Internet relativ begrenzt. Insbesondere die Benutzerdaten, die vom Sicherungsdienst verfügbar gemacht werden (z. B. SIP-URIs), sind für alle Mitarbeiter im Unternehmen über andere Mittel wie etwa das globale Adressbuch oder andere Verzeichnissoftware allgemein verfügbar. Daher sollte der Schwerpunkt auf dem Schutz des WANs zwischen den beiden Rechenzentren liegen, wenn der Sicherungsdienst zum Kopieren von Daten zwischen einem Poolpaar verwendet wird.
  
### <a name="mitigating-security-risks"></a>Minimieren von Sicherheitsrisiken

Es gibt viele Methoden zur Verbesserung der Sicherheit für den Sicherungsdienst-Datenverkehr. Dies liegt zwischen Einschränken des Zugriffs auf die Rechenzentren zum Sichern von WAN Transport zwischen zwei Rechenzentren. In den meisten Fällen können Unternehmen Bereitstellen von Skype für Business Server bereits die erforderliche Sicherheitsinfrastruktur erfüllt sein. Für Unternehmen, suchen Sie nach der Anleitung bietet Microsoft eine Lösung als ein Beispiel zum Erstellen eine sichere IT-Infrastruktur. Weitere Informationen hierzu finden Sie unter [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?LinkId=268544). 
  
Wir werden nicht impliziert, dass es die einzige Lösung ist noch wir implizieren, dass es sich um die bevorzugte Lösung für Skype für Business Server ist. Wir empfehlen, dass Unternehmen die Lösung wählen, die ihrem individuellen Bedarf am meisten entspricht, je nach ihrer IT-Sicherheitsinfrastruktur und ihren Sicherheitsanforderungen. In der Microsoft-Beispiellösung werden IPsec und Gruppenrichtlinien für die Server- und Domänenisolation verwendet.
  
Eine weitere mögliche Lösung besteht in der Verwendung von IPSec ausschließlich zur Sicherung der vom Sicherungsdienst selbst gesendeten Daten. Wenn Sie sich für diese Methode entscheiden, konfigurieren Sie die IPSec-Regeln für das SMB-Protokoll auf den folgenden Servern, wenn Pool A und Pool B zwei verbundene Front-End-Pools sind.
  
- Der SMB-Dienst (TCP/445) von jedem Front-End-Server in Pool A an den von Pool B verwendeten Dateispeicher.
    
- Der SMB-Dienst (TCP/445) von jedem Front-End-Server in Pool B an den von Pool A verwendeten Dateispeicher.
    
> [!CAUTION]
>  IPsec ist nicht als Ersatz für Sicherheit auf Anwendungsebene wie etwa SSL/TLS gedacht. Ein Vorteil der Verwendung von IPsec liegt darin, dass es Sicherheit für Netzwerkdatenverkehr für vorhandene Apps bereitstellen kann, ohne dass diese geändert werden müssen. Unternehmen, die nur den Transport zwischen den beiden Datenzentren absichern möchten sollten finden Sie in den jeweiligen Netzwerke Hardwareherstellern über Möglichkeiten zur sicheren WAN-Verbindungen mithilfe des Herstellers Equipment eingerichtet.
  
## <a name="see-also"></a>Siehe auch

[Bereitstellen Sie kombinierte Front-End-Pools für Disaster Recovery in Skype für Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)

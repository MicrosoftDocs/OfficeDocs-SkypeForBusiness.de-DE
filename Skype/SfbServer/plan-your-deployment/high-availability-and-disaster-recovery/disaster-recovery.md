---
title: Disaster Recovery des Front-End-Pools in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
description: Für Disaster Recovery bietet Skype for Business Server Pool-Kopplung mit Failover für den Fall, dass ein Pool ausfällt.
ms.openlocfilehash: cacc1609094cba06c311a40f2502b4453013941e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815943"
---
# <a name="front-end-pool-disaster-recovery-in-skype-for-business-server"></a>Disaster Recovery des Front-End-Pools in Skype for Business Server
 
Für Disaster Recovery bietet Skype for Business Server Pool-Kopplung mit Failover für den Fall, dass ein Pool ausfällt.
  
Für die robustesten Disaster Recovery-Optionen in Skype for Business Server stellen Sie Paare von Front-End-Pools auf zwei geografisch verteilten Websites bereit. Jeder Standort verfügt über einen Front-End-Pool, für den es einen entsprechenden Front-End-Pool am anderen Standort gibt. Beide Standorte sind aktiv, und der Sicherungsdienst ermöglicht die Datenreplikation in Echtzeit, damit die Pools synchronisiert bleiben. Weitere Informationen finden Sie unter [Bereitstellen gekoppelter Front-End-Pools für Disaster Recovery in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md) , wenn Sie die Kopplung von Front-End-Pools implementieren möchten.
  
![Zeigt Front-End-Pools an zwei verschiedenen Standorten, die miteinander gepaart sind](../../media/f74533c0-a10e-4f18-85a8-b9a008497573.jpg)
  
Falls der Pool an einem Standort ausfällt, können Sie für die Benutzer ein Failover von diesem Pool auf den Pool am anderen Standort vornehmen, von dem dann für alle Benutzer in beiden Pools Dienste bereitgestellt werden. Für die Kapazitätsplanung sollte bei einem Notfall jeder Pool in der Lage sein, die Arbeitsauslastung aller Benutzer in beiden Pools zu bewältigen.
  
Zwei Rechenzentren, die die als Paar bereitgestellten Front-End-Pools enthalten, können beliebig weit voneinander entfernt stehen. Wir empfehlen die Verwendung zweier Rechenzentren in derselben Weltregion mit Hochgeschwindigkeitsverbindung. 
  
Die Verwendung zweier Rechenzentren in verschiedenen Weltregionen ist zwar möglich, führt jedoch u. U. zu größeren Datenverlusten aufgrund von Wartezeiten bei der Datenreplikation.
  
Beachten Sie bei der Planung, welche Pools als Paar bereitgestellt werden, dass nur die folgenden Paarungen unterstützt werden:
  
- Enterprise Edition-Pools können nur mit anderen Enterprise Edition-Pools gepaart werden. Entsprechend können Standard Edition-Pools nur mit anderen Standard Edition-Pools gepaart werden.
    
- Physische Pools können nur mit anderen physischen Pools gepaart werden. Entsprechend können virtuelle Pools nur mit anderen virtuellen Pools gepaart werden.
    
- Gepaarte Pools müssen unter demselben grundlegenden Betriebssystem laufen.
    
Eine Paarung zweier Pools, die nicht diesen Empfehlungen entspricht, wird weder durch den Topologie-Generator noch durch die Topologieüberprüfung verhindert. Der Topologie-Generator lässt z. B. die Paarung eines Enterprise Edition-Pools mit einem Standard Edition-Pool zu. Diese Art von Paarung wird jedoch nicht unterstützt.
  
## <a name="backup-registrar-relationships-and-survivable-branch-appliances"></a>Backup-Registrar-Beziehungen und Survivable Branch-Appliances

Neben der Notfallwiederherstellung dienen die verbundenen Pools als Sicherungsregistrierungsstellen füreinander. Jeder Pool kann die Sicherung für nur einen anderen Front-End-Pool sein.
  
Auch wenn Beziehungen von Sicherungsregistrierungsstellen zwischen zwei Front-End-Pools 1:1 und symmetrisch sein müssen, kann jeder Front-End-Pool auch eine Sicherungsregistrierung für eine Reihe von Survivable Branch Appliances sein.
  
Beachten Sie, dass Skype for Business die Notfallwiederherstellung für Benutzer auf einer Survivable Branch Appliance unterstützt. Wenn ein Front-End-Pool ausfällt, der als Sicherung für eine Survivable Branch Appliance dient, werden die bei der Survivable Branch Appliance angemeldeten Benutzer in den Ausfallsicherheitsmodus versetzt, selbst nachdem die Benutzer auf dem Front-End-Pool auf den Backup-Front-End-Pool verschoben wurden.
  
## <a name="recovery-time-for-pool-failover-and-pool-failback"></a>Wiederherstellungsdauer bei einem Failover und Failback eines Pools

Bei Pool-Failover und Pool-Failback beträgt das Engineering-Ziel für das Wiederherstellungszeitziel (RTO) 15-20 Minuten. Dies ist der Zeitpunkt, zu dem ein Failover erfolgen muss, nachdem Administratoren festgestellt haben, dass ein Notfall aufgetreten ist, und die Failoververfahren gestartet werden. Es umfasst nicht die Zeit, die Administratoren zur Beurteilung der Situation und zur Entscheidungsfindung haben, und auch nicht die Zeit, die Benutzer sich nach Abschluss des Failovers erneut anmelden müssen.
  
Für Poolfailover und Poolfailbacks liegt das Entwicklungsziel für das Recovery Time Objective (RTO) bei 5 Minuten. Dies definiert die Zeitspanne, in der Daten aufgrund des Notfalls und aufgrund der Replikationswartezeit des Sicherungsdienstes verloren gehen können. Wenn beispielsweise ein Pool um 10:00 Uhr herunterfällt und die RPO 5 Minuten beträgt, werden die Daten in den Pool zwischen 9:55 Uhr geschrieben. und 10:00 A. M. möglicherweise nicht in den Backup-Pool repliziert und gehen verloren.
  
Bei allen RTO-und RPO-Nummern in diesem Dokument wird davon ausgegangen, dass sich die beiden Rechenzentren innerhalb desselben Welt Bereichs mit hoch Geschwindigkeits Transporten mit niedriger Latenz zwischen den beiden Standorten befinden. Diese Nummern werden für einen Pool mit 40.000-aktiven Benutzern und 200.000-Benutzern, die für Skype for Business aktiviert sind, in Bezug auf ein vordefiniertes Benutzermodell gemessen, bei dem es bei der Datenreplikation keinen Rückstand gibt. Sie unterliegen Änderungen auf der Grundlage von Leistungstests und-Validierungen.
  
## <a name="central-management-store-failover"></a>Failover des zentralen Verwaltungsspeichers

Der zentrale Verwaltungsspeicher enthält Konfigurationsdaten zu Servern und Diensten in Ihrer Bereitstellung. Jede Skype for Business Server-Bereitstellung umfasst einen zentralen Verwaltungsspeicher, der vom Back-End-Server eines Front-End-Pools gehostet wird.
  
Wenn Sie den Pool koppeln, der den zentralen Verwaltungsspeicher hostet, wird im Backup-Pool eine Datenbank des zentralen Speichers für den Sicherungs-Manager eingerichtet. Eine der beiden zentralen Verwaltungsspeicher Datenbanken ist zu einem beliebigen Zeitpunkt aktiv, und die andere ist ein Standbymodus. Der Inhalt wird vom Sicherungsdienst aus der aktiven Datenbank in den Standbymodus repliziert.
  
![Zeigt zwei Front-End-Pools, einen mit dem aktiven CMS-Speicher und den anderen mit dem passiven CMS-Sicherungsspeicher](../../media/aa479398-eb56-4854-8d50-1eff39c58a56.jpg)
  
Während eines Poolfailovers, von dem die Pools betroffen sind, die den zentralen Verwaltungsspeicher hosten, müssen Sie den zentralen Verwaltungsspeicher ändern, bevor Sie das Failover für den Front-End-Pool durchführen.
  
Nach der Behebung des Notfalls ist es nicht erforderlich, einen Failback des zentralen Verwaltungsspeichers durchzuführen. Der zentrale Verwaltungsspeicher kann in dem Pool bleiben, zu dem er geändert wurde.
  
Die Entwicklungsziele für den zentralen Verwaltungsspeicher sind 5 Minuten für die Wiederherstellungsdauer (Recovery Time Objective, RTO) und 5 Minuten für den Wiederherstellungspunkt (Recovery Point Objective, RPO).
  
## <a name="front-end-pool-pairing-data-security"></a>Datensicherheit beim Bilden von Front-End-Poolpaaren

Der Sicherungsdienst überträgt kontinuierlich Benutzerdaten und Konferenzinhalte zwischen zwei gepaarten Front-End-Pools. Zu den Benutzerdaten gehören SIP-URIs von Benutzern sowie Konferenzpläne, Kontaktlisten und Einstellungen. Zu Konferenzinhalten gehören hochgeladene Microsoft PowerPoint-Präsentationen sowie in Konferenzen genutzte Whiteboards.
  
Vom Quellpool werden die Daten aus dem lokalen Speicher exportiert, gezippt und zum Zielpool übertragen, wo sie entzippt und in den lokalen Speicher importiert werden. Der Sicherungsdienst geht davon aus, dass die Kommunikationsverbindung zwischen den beiden Rechenzentren innerhalb des Unternehmensnetzwerks besteht, das vor dem Internet geschützt ist. Daher werden die übertragenen Daten nicht zwischen den zwei Rechenzentren verschlüsselt und auch nicht innerhalb eines sicheren Protokolls, etwa HTTPS, nativ verschlüsselt. Daher ist ein man-in-the-Middle-Angriff durch internes Personal innerhalb des Unternehmensnetzwerks möglich.
  
Alle Unternehmen, die Skype for Business Server in mehreren Rechenzentren bereitstellen und das Disaster Recovery-Feature verwenden, müssen sicherstellen, dass der Datenverkehr zwischen Rechenzentren durch sein Unternehmens Intranet geschützt ist. Unternehmen, die ihren Datenverkehr vor internen Angriffen schützen möchten, müssen die Kommunikationsverbindungen zwischen den Rechenzentren schützen. Dies ist eine standardmäßige Voraussetzung, die auch viele andere Arten von vertraulichen Unternehmensdaten schützt, die zwischen Rechenzentren übertragen werden.
  
Das Risiko von Man-in-the-Middle-Angriffen innerhalb des Unternehmensnetzwerks besteht zwar, doch ist es im Vergleich zur Gefährdung des Datenverkehrs im Internet relativ begrenzt. Insbesondere die Benutzerdaten, die vom Sicherungsdienst verfügbar gemacht werden (z. B. SIP-URIs), sind für alle Mitarbeiter im Unternehmen über andere Mittel wie etwa das globale Adressbuch oder andere Verzeichnissoftware allgemein verfügbar. Daher sollte der Schwerpunkt auf dem Schutz des WANs zwischen den beiden Rechenzentren liegen, wenn der Sicherungsdienst zum Kopieren von Daten zwischen einem Poolpaar verwendet wird.
  
### <a name="mitigating-security-risks"></a>Minimieren von Sicherheitsrisiken

Sie haben viele Möglichkeiten, den Sicherheitsschutz für den Backup-Service-Datenverkehr zu verbessern. Dies reicht vom Einschränken des Zugriffs auf die Rechenzentren bis zum Sichern des WAN-Transports zwischen den beiden Rechenzentren. In den meisten Fällen verfügen Unternehmen, die Skype for Business Server einsetzen, möglicherweise bereits über die erforderliche Sicherheitsinfrastruktur. Für Unternehmen, die nach Anleitungen suchen, bietet Microsoft eine Lösung als Beispiel für die Erstellung einer sicheren IT-Infrastruktur. Ausführliche Informationen finden Sie [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?LinkId=268544)unter. 
  
Wir implizieren nicht, dass dies die einzige Lösung ist, und wir sagen auch nicht, dass dies die bevorzugte Lösung für Skype for Business Server ist. Wir empfehlen, dass Unternehmen die Lösung wählen, die ihrem individuellen Bedarf am meisten entspricht, je nach ihrer IT-Sicherheitsinfrastruktur und ihren Sicherheitsanforderungen. In der Microsoft-Beispiellösung werden IPsec und Gruppenrichtlinien für die Server- und Domänenisolation verwendet.
  
Eine weitere mögliche Lösung besteht in der Verwendung von IPSec ausschließlich zur Sicherung der vom Sicherungsdienst selbst gesendeten Daten. Wenn Sie sich für diese Methode entscheiden, konfigurieren Sie die IPSec-Regeln für das SMB-Protokoll auf den folgenden Servern, wenn Pool A und Pool B zwei verbundene Front-End-Pools sind.
  
- Der SMB-Dienst (TCP/445) von jedem Front-End-Server in Pool A an den von Pool B verwendeten Dateispeicher.
    
- Der SMB-Dienst (TCP/445) von jedem Front-End-Server in Pool B an den von Pool A verwendeten Dateispeicher.
    
> [!CAUTION]
>  IPsec ist nicht als Ersatz für Sicherheit auf Anwendungsebene wie etwa SSL/TLS gedacht. Ein Vorteil der Verwendung von IPsec liegt darin, dass es Sicherheit für Netzwerkdatenverkehr für vorhandene Apps bereitstellen kann, ohne dass diese geändert werden müssen. Unternehmen, die nur den Transport zwischen den beiden Rechenzentren sichern möchten, sollten ihre jeweiligen Netzwerkhardware Anbieter konsultieren, wie Sie sichere WAN-Verbindungen mithilfe der Geräte des Herstellers einrichten können.
  
## <a name="see-also"></a>Siehe auch

[Bereitstellen gekoppelter Front-End-Pools für Disaster Recovery in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)

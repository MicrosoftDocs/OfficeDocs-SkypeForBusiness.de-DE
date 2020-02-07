---
title: Versionsunterstützung
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: In diesem Artikel wird die Lebenszyklus Unterstützung für Microsoft Teams-Chatrooms erläutert.
ms.openlocfilehash: 0f445bf2500a01bf8ffddae569d176229bdcfde5
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825913"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams rooms-App-Versionsunterstützung
 
Die Microsoft Teams rooms-APP erhält Updates ein paar Mal pro Jahr. Jedes Update wird zwölf (12) Monate nach dem Veröffentlichungsdatum der allgemeinen Verfügbarkeit (GA) unterstützt. Der technische Support wird für die gesamten zwölf (12) Monate bereitgestellt. Die Supportstruktur ist jedoch dynamisch, wobei zwei unterschiedliche Phasen von der Verfügbarkeit der neuesten Version abhängig sind:

- \- **Phase "Wartung und kritische Updates** " Wenn Sie die neueste Version der Microsoft Teams rooms-app ausführen, erhalten Sie regelmäßige Updates, die *Sicherheits-und Wartungs* Updates enthalten.

- **Nur Sicherheitsupdates Phase** \- wenn eine neue Version der Microsoft Teams rooms-App veröffentlicht wird, verfügen ältere Versionen der APP über eine reduzierte Supportebene mit *Sicherheitsupdates nur* für den restlichen zwölf (12) Monate-Lebenszyklus.

> [!NOTE]
> Die aktuelle Version befindet sich immer in der Phase Wartung und kritische Updates. Wenn Sie auf einen Codefehler stoßen, der ein wichtiges Update gewährleistet, müssen Sie auch die neueste Version installiert haben, um eine Lösung zu erhalten. Alle anderen unterstützten Versionen sind nur berechtigt, Sicherheitsupdates zu erhalten.

Alle Unterstützung endet, nachdem der 12-Monats-Lebenszyklus für eine Version abgelaufen ist oder mehr als zwei Updates seither veröffentlicht wurden. Anschließend müssen Kunden auf eine unterstützte Version aktualisieren.

Alle Versionen sind in den Versionshinweisen für [Microsoft Teams-Chatrooms](rooms-release-note.md)aufgeführt.

## <a name="windows-10-release-support"></a>Windows 10-Release-Unterstützung

Für Microsoft Teams Rooms sind die Windows 10-Enterprise-oder Windows 10 Enterprise-SKUs unter halbjährlichen Kanal Wartungsoptionen erforderlich. Diese anderen Windows 10-Editionen werden nicht unterstützt:

- Windows 10 Enterprise Long Term Servicing Branch (LTSB)/Long Term Servicing Channel (LTSC) Editions
- Windows 10 Internet der Dinge (viel) Enterprise-LTSB/LTSC-Editionen
- jede andere Edition von Windows wie Windows 10 pro oder Home Edition

Ein Windows 10-Funktions Update wird auf den Microsoft Teams rooms-Geräten nicht sofort angeboten oder aktualisiert. Eine absichtliche Verzögerung von bis zu sechs Monaten nach dem allgemeinen Verfügbarkeitsdatum, das auf der [Windows 10-Veröffentlichungs Informations](https://docs.microsoft.com/windows/release-information/) Seite veröffentlicht wurde. Die Verzögerungszeit wird verwendet, um die Windows 10-Release-Kompatibilität für die Microsoft Teams rooms-Anwendung, die Gerätehardware und die zertifizierten Audio-Video-Peripheriegeräte zu überprüfen. Die Validierung beginnt und wird während der aktiven Entwicklung jeder Hauptversion von Windows 10 fortgesetzt. Es wird mehr Zeit benötigt, um zu überprüfen, ob alle Gerätehersteller aktualisierte Bilder für Ihre Geräte erstellt haben, und Microsoft Teams diese Bilder zertifizieren und testen. Während des Gültigkeits Prüfungszeitraums verwendet die Microsoft Teams Room-APP [Windows Update für Business-Gruppenrichtlinien](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) , um Windows 10-Funktionsupdates zu verzögern. Nachdem Kompatibilitätsprobleme gefunden und behoben wurden, wird der Block durch Aktualisieren von Gruppenrichtlinien über eine neue App-Version im Windows Store aufgehoben. Geräte, auf denen die Microsoft Teams rooms-app ausgeführt wird, werden beim nächtlichen Wartungs Neustart automatisch auf eine geeignete Windows 10-Version aktualisiert. Für Kunden, die Updates manuell verwalten möchten, wird eine MSI-Version bereitgestellt.  

> [!IMPORTANT]
> Während des Gültigkeitszeitraums sollten Microsoft Teams rooms-Geräte **auf keinen Fall** auf die nächste Version von Windows 10 aktualisiert werden. Dies umfasst das Überschreiben der Gruppenrichtlinien direkt oder die Verwendung von System Center oder anderen Geräte Verwaltungsdiensten von Drittanbietern. Dies kann zu Problemen bei der Microsoft Teams Room-Anwendung oder zu unbrauchbaren Geräten führen.  

In der folgenden Tabelle sind die empfohlenen und unterstützten Versionen von Windows 10 aufgeführt, die für die Unterstützung von Microsoft Teams-Räumen überprüft werden. Alle Datumsangaben sind im ISO 8601-Format aufgeführt: yyyy-mm-tt.

|Version  |Verfügbarkeitsdatum   |Support Status für Microsoft Teams rooms   |Microsoft Teams-Chatrooms, minimale Anwendungsversion | Empfohlener Betriebssystem-Build  |
|:---  |:---       |:---                                  |:---     |:---     |
| 1909 |2019-11-12 |Zurzeit überprüft, <br/>Nicht empfohlen|&#x2014; |&#x2014; |
| 1903 |2019-05-21 |Unterstützte #a0 <br/>Empfohlen  |4.2.4.0 |18362,356 |
| 1809 |2019-03-28 |Übersprungen <br/>Nicht empfehlenswert #a0|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |Unterstützt                             |4.1.22.0 |17134,191|
| 1709 |2018-01-18 |Nicht unterstützt                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |Nicht unterstützt                         |&#x2014; |&#x2014; |
||||||

&#x2780; Windows 10 1903 steht aufgrund eines Problems mit einem Intel-Grafikgeräte Treiber für Crestron Flex-Geräte nicht zur Verfügung. Windows 10 1903 wird auf diesen Geräten nicht angeboten. Benutzer sollten diese Geräte nicht auf 1903 aktualisieren und auf Windows 10 1803 aufbewahren, bis ein Grafiktreiber Update von Crestron zur Verfügung gestellt wird. 

&#x2781; die Windows 10 1809-Version wird aufgrund von Kompatibilitätsproblemen, die mit der Microsoft Teams rooms-Anwendung gefunden wurden, nicht empfohlen. Dieses spezielle Problem führt dazu, dass die Microsoft Teams rooms-Anwendung nach einem nächtlichen Neustart nicht gestartet werden konnte. Dieses Problem wurde in der Windows 10 1903-Version behoben.  

Wenn Sie eine unterstützte Version von Windows 10 verwenden, erhalten Sie immer die neuesten Anwendungsupdates für die Microsoft Teams rooms-app.  

## <a name="see-also"></a>Siehe auch

[Microsoft Teams Rooms-Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Versionsinformationen zu Microsoft Teams rooms](rooms-release-note.md)

[Planen von Microsoft Teams-Räumen](rooms-plan.md)

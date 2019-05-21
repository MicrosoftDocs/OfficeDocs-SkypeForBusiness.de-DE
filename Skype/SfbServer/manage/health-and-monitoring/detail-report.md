---
title: Konferenz Detail Bericht in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Zusammenfassung: erfahren Sie mehr über den Konferenz Detail Bericht, der in Skype for Business Server verwendet wird.'
ms.openlocfilehash: 5b88ae62c7d06437b3502bd72dd965fc26fbfcb6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305787"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a>Konferenz Detail Bericht in Skype for Business Server

**Zusammenfassung:** Informieren Sie sich über den Konferenz Detail Bericht, der in Skype for Business Server verwendet wird.

Der detaillierte Konferenzbericht enthält ausführliche Informationen zu allen Benutzern, die an einer Konferenz teilgenommen haben. Sie können beispielsweise Informationen wie Datum und Uhrzeit, an dem bzw. zu der ein Benutzer einer Konferenz beigetreten ist und die Konferenz verlassen hat, sowie den Benutzer-Agent des Endpunkts anzeigen, mit dem der Benutzer mit der Konferenz verbunden wurde. Darüber hinaus können Sie Informationen zu der Rolle des Benutzers in den einzelnen Konferenzen (z. B. Referent oder Teilnehmer) anzeigen. Der vielleicht wichtigste Aspekt ist, dass Sie auf einen Blick erkennen können, welche Benutzer der Konferenz erfolgreich beigetreten und sie abgeschlossen haben und welche Benutzer der Konferenz nicht beitreten konnten und sie daher nicht abgeschlossen haben.

## <a name="accessing-the-conference-detail-report"></a>Zugreifen auf den detaillierten Konferenzbericht

Auf den detaillierten Konferenzbericht kann über die folgenden Berichte zugegriffen werden:

- [Call Admission Control Report](call-admission-control-report.md) (durch Klicken auf die Metrik „Detail“ für eine Konferenz)

- [Failure List Report](failure-list-report.md) (durch Klicken auf die Metrik „Konferenz“)

- [User Activity Report](call-diagnostic-reports-per-user.md) (durch Klicken auf die Metrik „Konferenz-URI“)

Im Konferenz Detail Bericht können Sie auf den [Diagnose](diagnostic-report.md) -Repor zugreifen, indem Sie auf die Metrik Diagnosebericht (Detail) klicken.

## <a name="filters"></a>Filter

Keine. Der detaillierte Konferenzbericht lässt sich nicht filtern.

## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Informationen aus dem Abschnitt zu Konferenzinformationen des detaillierten Konferenzberichts aufgeführt.

**Konferenzinformationen – Metriken**


| **Name**                 | **Beschreibung**                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| **Konferenz-URI** <br/> | Der Konferenz zugewiesener URI. Beispiel:  <br/> sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4  <br/> |
| **Pool-FQDN** <br/>      | Vollqualifizierter Domänenname des Registrierungspools oder Edgeservers in einer Sitzung.  <br/>                             |
| **Startzeitpunkt** <br/>     | Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.  <br/>                                                                          |
| **Organisator** <br/>      | SIP-Adresse des Benutzers, der die Sitzung organisiert hat.  <br/>                                                               |
| **Endzeitpunkt** <br/>       | Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.  <br/>                                                                            |

In der folgenden Tabelle werden die Informationen aus dem Abschnitt zur Konferenzteilnahme des detaillierten Konferenzberichts aufgeführt.

**Konferenzteilnahme – Metriken**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**User** <br/> |SIP-Adresse des Benutzers, der an der Konferenz teilgenommen hat.  <br/> |
|**Rolle** <br/> |Rolle (z. B. Referent) des Konferenzteilnehmers.  <br/> |
|**Verbindung** <br/> |Netzwerkverbindungen (in der Regel „From Internal“ oder „From External“) des Teilnehmers.  <br/> |
|**Beitrittszeitpunkt** <br/> |Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.  <br/> |
|**Beendigungszeitpunkt** <br/> |Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer die Konferenz verlassen hat.  <br/> |
|**Benutzer-Agent** <br/> |Der Bezeichner für die Software, die vom Endpunkt des Teilnehmers verwendet wird.  <br/> |
|**Diagnoseberichte** <br/> |Enthält Diagnose- und Problembehandlungsinformationen, einschließlich SIP-Antwortcodes, Diagnoseheader, Zeitpunkt des Konferenzbeitritts und Diagnose-IDs für fehlgeschlagene Sitzungen.  <br/> |

In der folgenden Tabelle sind die Informationen aufgeführt, die im Abschnitt Konferenz Modalitäten des Konferenz Detail Berichts bereitgestellt werden.

**Konferenzmodalitäten – Metriken**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**User** <br/> |SIP-Adresse des Benutzers, der an der Konferenz teilgenommen hat.  <br/> |
|**Beitrittszeitpunkt** <br/> |Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.  <br/> |
|**Beendigungszeitpunkt** <br/> |Datum und Uhrzeit, an dem bzw. zu der ein Teilnehmer die Konferenz verlassen hat.  <br/> |
|**Konferenzserver-URI** <br/> |URI für den in der Konferenz verwendeten Konferenzserver.  <br/> |
|**Diagnoseberichte** <br/> |Enthält Diagnose- und Problembehandlungsinformationen, einschließlich SIP-Antwortcodes, Diagnoseheader, Zeitpunkt des Konferenzbeitritts und Diagnose-IDs für fehlgeschlagene Sitzungen.  <br/> |



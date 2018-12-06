---
title: Überprüfen der Konfiguration von Office Web Apps Server in Lync Server 2013
TOCTitle: Überprüfen der Konfiguration von Office Web Apps Server in Lync Server 2013
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205393(v=OCS.15)
ms:contentKeyID: 49295932
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen der Konfiguration von Office Web Apps Server in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-04-22_

Nachdem Office Web Apps Server der Topologie hinzugefügt und diese Topologie veröffentlicht wurde, sollten zwei neue Ereignisse im Lync Server-Ereignisprotokoll angezeigt werden. Als Erstes sollte ein "LS Data MCU"-Ereignis (Ereignis-ID 41034) hinzugefügt worden sein. Dieses Ereignis meldet, dass Office Web Apps Server erkannt wurde:

**Webkonferenzserver-WAC wurde ermittelt, PowerPoint-Inhalte sind aktiviert.**

Außerdem sollte ein weiteres "LS Data MCU"-Ereignis angezeigt werden (Ereignis-ID 41032), das Office Web Apps Server-URLs zurückmeldet. Beispielsweise sollten Meldungen wie etwa folgende angezeigt werden:

**Webkonferenzserver-WAC wurde ermittelt.**

**WAC-interne Referentenseite: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**WAC-interne Teilnehmerseite: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**WAC-externe Referentenseite: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**WAC-externe Teilnehmerseite: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

Wenn Sie ein "LS Data MCU"-Ereignise mit der Ereignis-ID\&nbsp;41033 sehen, bedeutet das, dass bei der Office Web Apps Server-Ermittlung ein Fehler aufgetreten ist. In diesem Fall versucht Microsoft Lync Server 2013 so oft wie erforderlich, den neuen konfigurierten Office Web Apps Server zu ermitteln. Führt der Ermittlungsprozess mehrmals nicht zum Erfolg, sollten Sie Office Web Apps Server aus dem Topologiedokument entfernen, die aktualisierte Topologie veröffentlichen und dann nach Beheben der Verbindungsprobleme versuchen, Office Web Apps Server wieder zu der Topologie hinzuzufügen.

Wenn Office Web Apps Server offensichtlich korrekt konfiguriert und vom Ermittlungsprozess erkannt worden ist, können Sie sicherstellen, dass Office Web Apps Server wie erwartet funktioniert, indem Sie eine PowerPoint-Präsentation zwischen einem Microsoft Lync 2013-Clientpaar freigeben. Wenn Benutzer\&nbsp;A die PowerPoint-Präsentation laden und anzeigen und Benutzer\&nbsp;B dann der Besprechung beitreten und die Präsentation sehen kann, funktioniert Office Web Apps Server einwandfrei.

Auch wenn Office Web Apps Server anscheinend korrekt konfiguriert ist, kann es sein, dass Sie die folgende Fehlermeldung erhalten, wenn Sie versuchen, eine PowerPoint-Präsentation freizugeben: "Einige Freigabefunktionen sind aufgrund von Serververbindungsproblemen nicht verfügbar". Wenn Sie diese Fehlermeldung erhalten, sollten Sie die Front-End-Server, die dem neuen Office Web Apps Server zugeordnet sind, neu starten.


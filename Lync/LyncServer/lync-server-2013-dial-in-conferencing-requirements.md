---
title: Anforderungen für Einwahlkonferenzen in Lync Server 2013
TOCTitle: Anforderungen für Einwahlkonferenzen in Lync Server 2013
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398802(v=OCS.15)
ms:contentKeyID: 49294874
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anforderungen für Einwahlkonferenzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-30_

Bevor Sie den Bereitstellungsprozess für Lync Server 2013 starten, müssen Sie Folgendes planen:

  - Die für die Verbindung mit dem Telefonfestnetz (Public Switched Telephone Network, PSTN) zu verwendende Konfiguration

  - Ihre Strategie für die Zuweisung von Regionen für Einwahlkonferenzen zu Einwahlnummern

  - Ihre Strategie für die Erstellung von Konferenzverzeichnissen

## Planen der Einwahl-PSTN-Konnektivität

Einwahlkonferenzen erfordern mindestens einen Vermittlungsserver und mindestens ein PSTN-Gateway.

Sie können einen Vermittlungsserver an einem zentralen Standort oder an einem Zweigstellenstandort bereitstellen. An einem zentralen Standort kann ein Vermittlungsserver in einem Front-End-Pool oder auf einem Standard Edition-Server gemeinsam ausgeführt oder auf einem eigenständigen Server oder in einem eigenständigen Pool bereitgestellt werden. An einem Zweigstellenstandort können Sie einen Vermittlungsserver auf einem eigenständigen Server oder als Komponente der Survivable Branch-Anwendung bereitstellen.

Sie können ein PSTN-Gateway an einem zentralen Standort oder an einem Zweigstellenstandort bereitstellen. An einem Zweigstellenstandort kann das PSTN-Gateway eigenständig oder als Komponente der Survivable Branch-Anwendung eingesetzt werden.


> [!NOTE]
> Einwahlkonferenzen verwenden keine Medienumgehung, da A/V-Konferenzserver keine Medienumgehung unterstützen.



Ausführliche Informationen zur Planung der Konfiguration für Vermittlungsserver und PSTN-Gateways für Einwahlkonferenzen finden Sie unter [Komponenten und Topologien für den Vermittlungsserver in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in der Planungsdokumentation.

## Planen von Regionen für Einwahlkonferenzen

Während der Einwahlkonfiguration erstellen Sie Wähleinstellungen und Zugriffsnummern für Einwahlkonferenzen. Wähleinstellungen sind Sätze von Normalisierungsregeln, in welchen die Anzahl und das Muster von Ziffern in einer Telefonnummern festgelegt wird und die die Telefonnummer in das Standard-E.164-Format zur Anrufweiterleitung übersetzen. Zugriffsnummern für Einwahlkonferenzen sind die Nummern, die Benutzer zur Teilnahme an Konferenzen wählen.

Jede Zugriffsnummer für Einwahlkonferenzen muss mindestens einem Satz mit Wähleinstellungen zugeordnet sein. Regionen für Einwahlkonferenzen ordnen eine Zugriffsnummer für Einwahlkonferenzen den entsprechenden Wähleinstellungen zu. Wenn Sie einen Satz mit Wähleinstellungen einrichten, geben Sie die Region für Einwahlkonferenzen an, die für diese Wähleinstellungen gilt. Wenn Sie anschließend die Zugriffsnummern für Einwahlkonferenzen erstellen, wählen Sie die Regionen aus, welche die Zugriffsnummern den geeigneten Wähleinstellungen zuordnen.

Beim Erstellen von Wähleinstellungen geben Sie den Gültigkeitsbereich der Wähleinstellungen an: Benutzer, Pool oder Standort. Jedem Benutzer werden die Wähleinstellungen aus dem am engsten gefassten Gültigkeitsbereich zugeordnet, der für den Benutzer gilt. Beispielsweise werden dem Benutzer Wähleinstellungen auf Benutzerebene zugewiesen, falls solche gelten. Gelten keine Wähleinstellungen auf Benutzerebene, werden dem Benutzer Wähleinstellungen auf Poolebene zugewiesen. Gelten keine Wähleinstellungen auf Poolebene, werden dem Benutzer Wähleinstellungen auf Standortebene zugewiesen. Gelten keine Wähleinstellungen auf Standortebene, werden dem Benutzer die globalen Wähleinstellungen zugewiesen.

Bevor Sie die Wähleinstellungen konfigurieren, ist es wichtig zu planen, wie die Regionen benannt und verwendet werden sollen. Für die Regionen von Einwahlkonferenzen gelten folgende Überlegungen:

  - Eine Region ist in der Regel ein geografischer Bereich, der einem Büro oder einer Gruppe von Büros zugeordnet wird.

  - Den Einwahlnummern werden Sprachen zugeordnet. Wenn Sie geografische Bereiche mit mehreren Sprachen unterstützen, sollten Sie entscheiden, wie die Regionen für die Unterstützung der verschiedenen Sprachen definiert werden sollen. Beispielsweise können Sie mehrere Regionen basierend auf einer Kombination aus Geografie und Sprache definieren, oder Sie können eine einzige Region basierend auf der Geografie definieren und für jede Sprache eine eigene Einwahlnummer verwenden.

  - Wenn ein Benutzer eine Besprechung plant, wird für die Besprechung standardmäßig die Region verwendet, die durch die Wähleinstellungen des Benutzers festgelegt ist.

  - Standardmäßig sind in der Besprechungseinladung alle Einwahlnummern für die Region enthalten.

  - Regionen müssen unbedingt so benannt werden, dass sie klar erkennbar sind. Der Benutzer kann anhand der Regionsnamen die Region einer Besprechung ändern, damit in der Einladung andere Zugriffsnummern enthalten sind. (Bei Verwendung von Outlook zum Planen einer Besprechung nutzt der Benutzer das Onlinebesprechungs-Add-In für Lync 2013 zum Ändern der Region.)

  - Regionen sollten so konzipiert werden, dass jedem eingeladenen Benutzer, der sich in eine Konferenz einwählen möchte, eine lokale Zugriffsnummer in der Konferenzeinladung angezeigt wird.

  - Mithilfe der Cmdlets in der Lync Server-Verwaltungsshell können Sie die Reihenfolge konfigurieren, in der Zugriffsnummern innerhalb einer Region auf der Seite "Einstellungen für Einwahlkonferenz" angezeigt werden (und somit die Reihenfolge, in der sie in der Konferenzeinladung aufgeführt sind).

  - Jeder Benutzer kann an jedem beliebigen Standort eine beliebige Einwahlnummer wählen, um an einer Konferenz teilzunehmen.

## Planen von Konferenzverzeichnissen

In Konferenzverzeichnissen wird eine Zuordnung der alphanumerischen Besprechungs-ID, die ein Teilnehmer bei Verwendung von Lync 2013 zum Beitreten zu einer Konferenz nutzt, und der rein numerischen Konferenz-ID verwaltet, die ein Einwahlkonferenzteilnehmer zum Beitreten zur Konferenz verwendet. Das Format der Konferenz-ID lautet folgendermaßen:

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

Indem mehrere Konferenzverzeichnisse erstellt werden, wird sichergestellt, dass Konferenz-IDs kurz bleiben, solange keine sehr große Anzahl Konferenzen erstellt wurde. Um etwa sechsstellige Konferenz-IDs zu erhalten, wird in einer Organisation mit einer typischen Konferenzanzahl pro Benutzer empfohlen, pro 999 Benutzer im Pool je ein Konferenzverzeichnis zu erstellen. Wenn diese Richtlinie eingehalten wird, bleiben die Konferenz-IDs in der Regel kurz. Sobald die Anzahl der Konferenzverzeichnisse (in den Pools) neun übersteigt, wird die Konferenz-ID-Nummer jedoch größer, um zusätzliche Konferenzen zu unterstützen.

## Siehe auch

#### Konzepte

[Vermittlungsserverkomponente in Lync Server 2013](lync-server-2013-mediation-server-component.md)  
[Wählpläne und Normalisierungsregeln in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)


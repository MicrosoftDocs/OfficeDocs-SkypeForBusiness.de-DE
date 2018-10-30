---
title: 'Lync Server 2013: Konfigurieren von Konferenzrichtlinien für die Einwahl'
TOCTitle: Konfigurieren von Konferenzrichtlinien für die Einwahl
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398810(v=OCS.15)
ms:contentKeyID: 49294883
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Konferenzrichtlinien für die Einwahl in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-03-21_

Die Konferenzrichtlinie ist eine Benutzerkontoeinstellung, die die Konferenzmöglichkeiten für Teilnehmer festlegt. Sie können Konferenzrichtlinien auf Standort- oder Benutzerebene erstellen. Konferenzrichtlinieneinstellungen umfassen viele Aspekte der Konferenzplanung und -teilnahme. Mehrere Konferenzrichtlinieneinstellungen unterstützen Einwahlkonferenzen für Teilnehmer. Bei der Konfiguration von Einwahlkonferenzen sollten Sie sicherstellen, dass diese Felder für Ihre Organisation angemessen festgelegt sind, und sie bei Bedarf bearbeiten.

Überprüfen Sie in Ihrer Konferenzrichtlinie die folgenden Felder:

  - **Teilnehmern das Einladen anonymer Benutzer gestatten**    Diese Einstellung erlaubt den Besprechungsorganisatoren das Einladen anonymer (also nicht authentifizierter) Besprechungsteilnehmer. Diese Einstellung ist für Einwahlkonferenzen optional. Diese Einstellung ist in der globalen Standardkonferenzrichtlinie standardmäßig ausgewählt.

  - **PSTN-Einwahlkonferenzen aktivieren**    Diese Einstellung ermöglicht Benutzern die Teilnahme am Audioteil einer Konferenz, indem sie sich vom Telefonfestnetz aus einwählen. Diese Einstellung ist für Einwahlkonferenzen erforderlich. Diese Einstellung ist in der globalen Standardkonferenzrichtlinie standardmäßig ausgewählt.

  - **Ausgehende Verbindung für anonyme Teilnehmer zulassen**    Diese Einstellung ermöglicht anonymen Benutzern, die bereits an einer Besprechung teilnehmen, eine ausgehende Telefonnummer zu wählen, um am Audioteil der Konferenz teilzunehmen. Diese Einstellung ist für Einwahlkonferenzen optional. Diese Einstellung ist in der globalen Standardkonferenzrichtlinie standardmäßig nicht ausgewählt.

  - **Ausgehende Verbindung für Teilnehmer zulassen, die nicht für Enterprise-VoIP aktiviert sind**    Diese Einstellung ermöglicht Teilnehmern und Organisatoren von Besprechungen, die nicht für Enterprise-VoIP aktiviert sind, eine ausgehende Telefonnummer zu wählen, um am Audioteil der Konferenz teilzunehmen. Der ausgehende Anruf wird auf der Grundlage der dem Organisator zugewiesenen VoIP-Richtlinie autorisiert. Diese Einstellung ist in der globalen Standardkonferenzrichtlinie standardmäßig nicht ausgewählt. Diese Einstellung ist standardmäßig deaktiviert.
    

    > [!NOTE]
    > Damit ein Organisator, der nicht für Enterprise-VoIP aktiviert ist, diese Möglichkeit aktivieren kann, muss ihm eine entsprechende VoIP-Richtlinie zugewiesen sein, die ihn autorisiert, bei einer durch einen Benutzer organisierten Konferenz ausgehende Anrufe durchzuführen. Eine VoIP-Richtlinie kann einem Benutzer, der nicht für Enterprise-VoIP aktiviert ist, über die Lync Server-Verwaltungsshell zugewiesen werden. Wenn dem Benutzer nicht explizit eine VoIP-Richtlinie zugewiesen wurde, wird die VoIP-Richtlinie des Standorts verwendet, um die Auswahlanforderung zu autorisieren.&nbsp;Gibt es keine Standortrichtlinie, wird die globale VoIP-Richtlinie verwendet.



Das in diesem Abschnitt beschriebene Verfahren erläutert, wie die Konferenzrichtlinie geändert wird. Ausführliche Informationen zur Konfiguration aller Einstellungen, die in der Standardkonferenzrichtlinie das Erlebnis der Teilnehmer definieren, finden Sie unter [Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Besprechungen](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md). Ausführliche Informationen zum Erstellen einer Konferenzrichtlinie für einen bestimmten Benutzer oder eine bestimmt Benutzergruppe finden Sie unter [Erstellen oder Ändern einer Konferenzrichtlinie in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md). Eine Liste aller verfügbaren Konferenzrichtlinieneinstellungen finden Sie unter [Referenz zu den Konferenzrichtlinieneinstellungen](lync-server-2013-conferencing-policy-settings-reference.md).

## So ändern Sie die Konferenzrichtlinie für die Einwahl

1.  Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-ServerAdministrator** oder **CsAdministrator** an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenz** .

4.  Doppelklicken Sie auf der Registerkarte **Konferenzrichtlinie** auf den Namen einer Konferenzrichtlinie, um das Dialogfeld **Konferenzrichtlinie bearbeiten** zu öffnen.

5.  Stellen Sie sicher, dass die Felder für Einwahlkonferenzen für Ihre Organisation angemessen eingestellt sind, und ändern Sie die Einstellungen bei Bedarf.

6.  Klicken Sie auf **Commit** .


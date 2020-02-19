---
title: 'Lync Server 2013: Konfigurieren der konferenzrichtlinie für die Einwahl'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a74d49797565f643e36dfc59956ecc3ad73824e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a>Konfigurieren von Konferenzrichtlinien für die Einwahl in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-03-21_

Die Konferenzrichtlinie ist eine Benutzerkontoeinstellung, die die Konferenzmöglichkeiten für Teilnehmer festlegt. Sie können Konferenzrichtlinien auf Standort- oder Benutzerebene erstellen. Konferenzrichtlinieneinstellungen umfassen viele Aspekte der Konferenzplanung und -teilnahme. Mehrere Konferenzrichtlinieneinstellungen unterstützen Einwahlkonferenzen für Teilnehmer. Bei der Konfiguration von Einwahlkonferenzen sollten Sie sicherstellen, dass diese Felder für Ihre Organisation angemessen festgelegt sind, und sie bei Bedarf bearbeiten.

Überprüfen Sie in Ihrer Konferenzrichtlinie die folgenden Felder:

  - **Teilnehmer dürfen anonyme Benutzer**   einladen mit dieser Einstellung können Besprechungsorganisatoren anonyme (nicht authentifizierte) Teilnehmer zu Besprechungen einladen. Diese Einstellung ist für Einwahlkonferenzen optional. Diese Einstellung ist in der globalen Standardkonferenzrichtlinie standardmäßig ausgewählt.

  - **PSTN-Einwahlkonferenzen**   aktivieren mit dieser Einstellung können Benutzer am Audioteil einer Konferenz teilnehmen, indem Sie sich über das PSTN einwählen. Diese Einstellung ist für Einwahlkonferenzen erforderlich. Diese Einstellung ist in der globalen Standardkonferenzrichtlinie standardmäßig ausgewählt.

  - **Anonymen Teilnehmern**   das auswählen erlauben diese Einstellung ermöglicht es anonymen Benutzern, die sich bereits mit der Besprechung verbunden haben,, eine Telefonnummer für die Teilnahme am Audioteil der Konferenz zu wählen. Diese Einstellung ist für Einwahlkonferenzen optional. Diese Einstellung ist in der globalen Standardkonferenzrichtlinie standardmäßig nicht ausgewählt.

  - **Teilnehmern, die nicht für Enterprise-VoIP aktiviert sind,**   das auswählen erlauben mit dieser Einstellung können Besprechungsteilnehmer und Organisatoren, die nicht für Enterprise-VoIP aktiviert sind, eine Telefonnummer für die Teilnahme am Audioteil der Konferenz wählen. Der ausgehende Anruf wird auf der Grundlage der dem Organisator zugewiesenen VoIP-Richtlinie autorisiert. Diese Einstellung ist in der globalen Standardkonferenzrichtlinie standardmäßig nicht ausgewählt. Diese Einstellung ist standardmäßig deaktiviert.
    
    <div>
    

    > [!NOTE]  
    > Um diese Funktion zu aktivieren, sollte einem Besprechungsorganisator, der nicht für Enterprise-VoIP aktiviert ist, eine entsprechende VoIP-Richtlinie zugewiesen sein, um alle Auswahlen einer von diesem Benutzer organisierten Konferenz zu autorisieren. Eine VoIP-Richtlinie kann einem Benutzer zugewiesen werden, der nicht für Enterprise-VoIP aus dem lync Server-Verwaltungsshell aktiviert ist. Wenn dem Benutzer keine VoIP-Richtlinie explizit zugewiesen wurde, wird die VoIP-Richtlinie verwendet, um die Auswähl Anforderung zu autorisieren. Wenn keine VoIP-Richtlinie für Websites vorhanden ist, wird die globale VoIP-Richtlinie verwendet.&nbsp;

    
    </div>

Das in diesem Abschnitt beschriebene Verfahren erläutert, wie die Konferenzrichtlinie geändert wird. Ausführliche Informationen zum Konfigurieren aller Einstellungen, die die Teilnehmer Erfahrung in der Standard konferenzrichtlinie definieren, finden Sie unter [erstellen oder Ändern einer Sammlung von Besprechungs Konfigurationseinstellungen in lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md). Ausführliche Informationen zum Erstellen einer konferenzrichtlinie für einen bestimmten Benutzer oder eine bestimmte Gruppe von Benutzern finden Sie unter [erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md). Eine Liste aller verfügbaren konferenzrichtlinieneinstellungen finden Sie unter [Conferencing Policy Settings Reference for lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a>So ändern Sie die Konferenzrichtlinie für die Einwahl

1.  Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-ServerAdministrator** oder **CsAdministrator** an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenz**.

4.  Doppelklicken Sie auf der Registerkarte **Konferenzrichtlinie** auf den Namen einer Konferenzrichtlinie, um das Dialogfeld **Konferenzrichtlinie bearbeiten** zu öffnen.

5.  Stellen Sie sicher, dass die Felder für Einwahlkonferenzen für Ihre Organisation angemessen eingestellt sind, und ändern Sie die Einstellungen bei Bedarf.

6.  Klicken Sie auf **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>


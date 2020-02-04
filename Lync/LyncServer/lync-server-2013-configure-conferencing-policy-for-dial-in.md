---
title: 'Lync Server 2013: Konfigurieren von Konferenzrichtlinien für die Einwahl'
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
ms.openlocfilehash: 107c5fcf4b341c652cd4044fe47f4b650cf5adb4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a>Konfigurieren von Konferenzrichtlinien für die Einwahl in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-03-21_

Die Konferenzrichtlinie ist eine Benutzerkontoeinstellung, die die Konferenzmöglichkeiten für Teilnehmer festlegt. Sie können Konferenzrichtlinien auf Standort- oder Benutzerebene erstellen. Konferenzrichtlinieneinstellungen umfassen viele Aspekte der Konferenzplanung und -teilnahme. Mehrere Konferenzrichtlinieneinstellungen unterstützen Einwahlkonferenzen für Teilnehmer. Bei der Konfiguration von Einwahlkonferenzen sollten Sie sicherstellen, dass diese Felder für Ihre Organisation angemessen festgelegt sind, und sie bei Bedarf bearbeiten.

Überprüfen Sie die folgenden Felder in ihrer konferenzrichtlinie:

  - **Teilnehmern erlauben, anonyme Benutzer**   einzuladen diese Einstellung ermöglicht es Besprechungsorganisatoren, anonyme (nicht authentifizierte) Teilnehmer zu Besprechungen einzuladen. Diese Einstellung ist für Einwahlkonferenzen optional. Diese Einstellung ist standardmäßig in der globalen Standard konferenzrichtlinie aktiviert.

  - **Aktivieren von PSTN-Einwahlkonferenzen**   mit dieser Einstellung können Benutzer am Audioteil einer Konferenz teilnehmen, indem Sie sich über das PSTN einwählen. Diese Einstellung ist für Einwahlkonferenzen erforderlich. Diese Einstellung ist standardmäßig in der globalen Standard konferenzrichtlinie aktiviert.

  - **Anonyme Teilnehmer erlauben, sich**   zu wählen diese Einstellung ermöglicht anonymen Benutzern, die bereits der Besprechung beigetreten sind, eine Telefonnummer zu wählen, um an dem Audioteil der Konferenz teilzunehmen. Diese Einstellung ist für Einwahlkonferenzen optional. Diese Einstellung ist in der standardmäßigen globalen konferenzrichtlinie nicht standardmäßig aktiviert.

  - **Teilnehmern, die für Enterprise-VoIP nicht aktiviert sind, erlauben,**   diese Einstellung zu wählen, ermöglicht es Besprechungsteilnehmern und Organisatoren, die nicht für Enterprise-VoIP aktiviert sind, eine Telefonnummer zu wählen, um am Audioteil der Konferenz teilzunehmen. Der Wähl Anruf ist basierend auf der zugewiesenen VoIP-Richtlinie des Organisators autorisiert. Diese Einstellung ist in der standardmäßigen globalen konferenzrichtlinie nicht standardmäßig aktiviert. Der Standardwert für die Einstellung ist deaktiviert.
    
    <div>
    

    > [!NOTE]  
    > Um diese Funktion zu aktivieren, sollte einem Besprechungsorganisator, der für Enterprise-VoIP nicht aktiviert ist, eine entsprechende VoIP-Richtlinie zugewiesen werden, um die Auswahl einer von diesem Benutzer organisierten Konferenz zu autorisieren. Eine VoIP-Richtlinie kann einem Benutzer zugewiesen werden, der in der lync Server-Verwaltungsshell nicht für Enterprise-VoIP aktiviert ist. Wenn dem Benutzer nicht explizit eine VoIP-Richtlinie zugewiesen ist, wird die Richtlinie für die Sprachausgabe verwendet, um die Auswähl Anforderung zu autorisieren. Wenn keine Website VoIP-Richtlinie vorhanden ist, wird die globale VoIP-Richtlinie verwendet.&nbsp;

    
    </div>

In diesem Abschnitt wird erläutert, wie Konferenzrichtlinien geändert werden. Details zum Konfigurieren aller Einstellungen, die die Teilnehmer Erfahrung in der Standard konferenzrichtlinie definieren, finden Sie unter [erstellen oder Ändern einer Sammlung von Einstellungen für die besprechungskonfiguration in lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md). Details zum Erstellen einer konferenzrichtlinie für einen bestimmten Benutzer oder eine Benutzergruppe finden Sie unter [erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md). Eine Liste aller verfügbaren konferenzrichtlinieneinstellungen finden Sie unter [Konferenzrichtlinien Einstellungsreferenz für lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a>So ändern Sie die konferenzrichtlinie für die Einwahl

1.  Melden Sie sich bei dem Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der Rolle **CS-ServerAdministrator** oder **CsAdministrator** an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenz**.

4.  Doppelklicken Sie auf der Registerkarte **konferenzrichtlinie** auf einen Konferenzrichtlinien Namen, um das Dialogfeld **konferenzrichtlinie bearbeiten** zu öffnen.

5.  Überprüfen Sie, ob die Felder für Einwahlkonferenzen für Ihre Organisation geeignet sind, und ändern Sie bei Bedarf die Einstellungen.

6.  Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>


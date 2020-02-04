---
title: 'Lync Server 2013: Erstellen oder Ändern einer konferenzrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing policy
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49733844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f3dd712b94838382f6022de888383c0f47bee6e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-policy-in-lync-server-2013"></a>Erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-07_

Führen Sie die folgenden Schritte aus, um eine konferenzrichtlinie auf Benutzerebene oder auf Websiteebene zu erstellen. Ausführliche Informationen zum Zuweisen einer Richtlinie auf Benutzerebene zu einem Benutzer finden Sie unter [Zuweisen einer konferenzrichtlinie für einzelne Benutzer in lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md). Eine Liste aller verfügbaren konferenzrichtlinieneinstellungen finden Sie unter [Konferenzrichtlinien Einstellungsreferenz für lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>

## <a name="to-create-a-new-user-or-site-policy"></a>So erstellen Sie einen neuen Benutzer oder eine neue Website Richtlinie

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** , und klicken Sie dann auf **konferenzrichtlinie**.

4.  Klicken Sie auf **Neu** und führen Sie eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Hinzufügen**, um eine Richtlinie auf Benutzerebene zu erstellen. Geben Sie im Abschnitt **Neue Konferenzrichtlinie** bei **Name** einen beschreibenden Namen für die Richtlinie ein.
    
      - Klicken Sie auf **Standortrichtlinie**, um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Suchfeld **Standort auswählen** einen Teil oder den gesamten Namen des Standorts ein, für den Sie eine Richtlinie erstellen möchten. Klicken Sie in der Liste der Standorte auf den gewünschten Standort und klicken Sie auf **OK**.
        
        <div>
        

        > [!NOTE]  
        > Der Websitename wird zum Namen der konferenzrichtlinie und kann nicht geändert werden.

        
        </div>

5.  Geben Sie bei **Beschreibung** eine Beschreibung für die Richtlinie ein.

6.  Geben Sie bei **Richtlinie für Organisatoren** unter **Maximale Besprechungsgröße** die Höchstzahl an Benutzern ein, die für eine Besprechung zugelassen werden sollen. Der maximale Besprechungsumfang ist standardmäßig auf 250 festgelegt.

7.  Um Benutzer daran zu hindern, anonyme Benutzer zu Besprechungen einzuladen, deaktivieren Sie das Kontrollkästchen **Teilnehmer dürfen anonyme Benutzer einladen**. Anonyme Benutzer sind Benutzer, die keine Anmeldeinformationen in den Active Directory-Domänendiensten Ihrer Organisation haben und daher nicht authentifiziert sind. In der Standardeinstellung können Benutzer anonyme Benutzer zu Besprechungen einladen.

8.  Führen Sie im Abschnitt **Aufzeichnung** eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Keine**, um Teilnehmer an der Aufzeichnung von Besprechungen zu hindern. Dies ist die Standardeinstellung.
    
      - Klicken Sie auf **Aufzeichnung aktivieren**, um Teilnehmern die Aufzeichnung von Besprechungen zu gestatten.

9.  Um externen Teilnehmern das Aufzeichnen von Besprechungen zu erlauben, aktivieren Sie das Kontrollkästchen **Partnerteilnehmern und anonymen Teilnehmern das Aufzeichnen gestatten**. In der Standardeinstellung werden externe Teilnehmer an der Aufzeichnung von Besprechungen gehindert.

10. Führen Sie im Abschnitt **Audio/Video** eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Keine**, um die Verwendung von Audio und Video zu verhindern.
    
      - Klicken Sie auf **IP-Audio aktivieren**, um die Verwendung von Audio, nicht jedoch von Video, zuzulassen.
    
      - Klicken Sie auf **IP-Audio/Video aktivieren**, um die Verwendung von Audio und Video zuzulassen. Dies ist die Standardeinstellung.

11. Wenn Sie die Verwendung von Audio im Abschnitt **Audio/Video** zulassen, führen Sie eine der folgenden Aufgaben aus:
    
      - Wenn Sie Benutzer daran hindern möchten, per Einwahl an einer Besprechung teilzunehmen, deaktivieren Sie das Kontrollkästchen **PSTN-Einwahlkonferenzen aktivieren**. In der Standardeinstellung können Benutzer sich über das Festnetz (Public Switched Telephone Network, PSTN) in Besprechungen einwählen.
    
      - Wenn Sie Benutzern die Einwahl in Besprechungen gestatten und nicht authentifizierten (anonymen) Benutzern die Teilnahme an Besprechungen über eine ausgehende Telefonverbindung erlauben möchten, aktivieren Sie das Kontrollkästchen **Anonyme Teilnehmer dürfen ausgehende Verbindungen herstelle**. Bei ausgehenden Telefonverbindungen ruft der Konferenzserver den Benutzer an und der Benutzer nimmt das Gespräch an, um an der Besprechung teilzunehmen. In der Standardeinstellung können anonyme Benutzer nicht über ausgehende Telefonverbindungen an Besprechungen teilnehmen.

12. Wenn Sie die Verwendung von Video in **Audio/Video**zulassen ausgewählt haben, aktivieren Sie **mehrere Videostreams zulassen** .

13. Führen Sie im Abschnitt **Datenzusammenarbeit** eine der folgenden Aktionen aus:
    
      - Wenn Sie keine Datenzusammenarbeit zulassen möchten, klicken Sie auf **Keine**.
    
      - Zum Zulassen einer Datenzusammenarbeit klicken Sie auf **Datenzusammenarbeit aktivieren**. Dies ist die Standardeinstellung.

14. Wenn Sie die Datenzusammenarbeit im Abschnitt **Datenzusammenarbeit** zulassen, führen Sie eine der folgenden Aufgaben aus:
    
      - Deaktivieren Sie das Kontrollkästchen **Partnerteilnehmer und anonyme Teilnehmer dürfen Inhalte herunterladen**. In der Standardeinstellung können externe Benutzer Inhalte herunterladen.
    
      - Deaktivieren Sie das Kontrollkästchen **Teilnehmer dürfen Dateien übertragen**, um Dateiübertragungen zu verhindern. In der Standardeinstellung können Dateien übertragen werden.
    
      - Deaktivieren Sie das Kontrollkästchen **Anmerkungen aktivieren**, um die Verwendung von Anmerkungen zu verhindern. Wenn Sie Anmerkungen in PowerPoint-Präsentationen verwenden möchten, deaktivieren Sie die **Option PowerPoint-Anmerkungen aktivieren**. In der Standardeinstellung sind Anmerkungen zulässig.
    
      - Deaktivieren Sie das Kontrollkästchen **Abstimmungen aktivieren**, um die Verwendung von Abstimmungen zu verhindern. In der Standardeinstellung sind Abstimmungen zulässig.

15. Führen Sie im Abschnitt **Anwendungsfreigabe** eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Anwendungsfreigabe deaktivieren**, um die Verwendung der Anwendungsfreigabe zu verhindern.
    
      - Klicken Sie auf **Anwendungsfreigabe aktivieren**, um die Verwendung der Anwendungsfreigabe zuzulassen. Dies ist die Standardeinstellung.

16. Wenn Sie die Anwendungsfreigabe im Abschnitt **Anwendungsfreigabe** zulassen, führen Sie eine der folgenden Aufgaben aus:
    
      - Deaktivieren Sie das Kontrollkästchen **Teilnehmer dürfen die Steuerung übernehmen**, um Teilnehmer an der Übernahme der Steuerung für die Anwendungsfreigabe zu hindern. In der Standardeinstellung können Teilnehmer die Steuerung für die Anwendungsfreigabe übernehmen.
    
      - Wenn Sie Besprechungsteilnehmern die Übernahme der Steuerung für die Anwendungsfreigabe ermöglichen möchten, aktivieren Sie das Kontrollkästchen **Partnerteilnehmer und anonyme Teilnehmer dürfen die Steuerung übernehmen**, um externen Benutzern die Übernahme der Steuerung für die Anwendungsfreigabe zu erlauben. In der Standardeinstellung können externe Benutzer die Steuerung für die Anwendungsfreigabe nicht übernehmen.

17. Führen Sie unter **Richtlinie für Teilnehmer** eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Anwendungs- und Desktopfreigabe deaktivieren**, um sowohl eine Anwendungsfreigabe als auch die Freigabe des Desktops zu verhindern.
    
      - Klicken Sie auf **Anwendungsfreigabe aktivieren**, um eine Anwendungsfreigabe, nicht jedoch die Freigabe des Desktops zu ermöglichen.
    
      - Klicken Sie auf **Anwendungs- und Desktopfreigabe aktivieren**, um sowohl eine Anwendungsfreigabe als auch die Freigabe des Desktops zuzulassen. Dies ist die Standardeinstellung.

18. Deaktivieren Sie das Kontrollkästchen **Peer-zu-Peer-Dateiübertragung aktivieren**, um Peer-zu-Peer-Dateiübertragungen zu verhindern. In der Standardeinstellung sind Peer-zu-Peer-Dateiübertragungen zulässig.

19. Aktivieren Sie das Kontrollkästchen **Peer-zu-Peer-Aufzeichnung aktivieren**, um eine Peer-zu-Peer-Aufzeichnung zuzulassen. In der Standardeinstellung sind Peer-zu-Peer-Aufzeichnungen unzulässig.

20. Aktivieren Sie das Kontrollkästchen **Teilnahme mit mehreren Videostreams aktivieren**, um die Teilnahme mit mehreren Videostreams zuzulassen. In der Standardeinstellung sind mehrere Videostreams zulässig.

21. Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="to-modify-an-existing-user-or-site-policy"></a>So ändern Sie einen vorhandenen Benutzer oder eine Website Richtlinie

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** , und klicken Sie dann auf **konferenzrichtlinie**.

4.  Klicken Sie in der Liste mit den Konferenzrichtlinien auf die Richtlinie, die Sie ändern möchten, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.

5.  Ändern Sie im Abschnitt **Konferenzrichtlinie bearbeiten** eine beliebige der Richtlinieneinstellungen. Hiervon ausgenommen ist der Richtlinienname, dieser kann nicht geändert werden.

6.  Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>


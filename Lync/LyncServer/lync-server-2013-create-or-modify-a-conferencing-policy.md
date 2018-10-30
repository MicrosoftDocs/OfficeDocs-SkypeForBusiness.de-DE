---
title: Erstellen oder Ändern einer Konferenzrichtlinie in Lync Server 2013
TOCTitle: Erstellen oder Ändern einer Konferenzrichtlinie in Lync Server 2013
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49890976
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern einer Konferenzrichtlinie in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-07_

Führen Sie die folgenden Schritte aus, um eine Konferenzrichtlinie auf Benutzer- oder Standortebene zu erstellen. Weitere Informationen zum Zuweisen einer Richtlinie auf Benutzerebene finden Sie unter [Zuweisen einer Konferenzrichtlinie auf Benutzerebene](lync-server-2013-assign-a-per-user-conferencing-policy.md). Eine Liste aller verfügbaren Konferenzrichtlinieneinstellungen finden Sie unter [Referenz zu den Konferenzrichtlinieneinstellungen](lync-server-2013-conferencing-policy-settings-reference.md).

## So erstellen Sie eine neue Benutzer- oder Standortrichtlinie

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **Konferenzrichtlinie**.

4.  Klicken Sie auf **Neu**, und führen Sie eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Hinzufügen**, um eine Richtlinie auf Benutzerebene zu erstellen. Geben Sie im Abschnitt **Neue Konferenzrichtlinie** in **Name** einen beschreibenden Namen für die Richtlinie ein.
    
      - Klicken Sie auf **Standortrichtlinie**, um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Suchfeld **Standort auswählen** einen Teil oder den gesamten Namen des Standorts ein, für den Sie eine Richtlinie erstellen möchten. Klicken Sie in der Liste der Standorte auf den gewünschten Standort, und klicken Sie auf **OK**.
        

        > [!NOTE]
        > Der Standortname wird als Name der Konferenzrichtlinie übernommen und kann nicht geändert werden.



5.  Geben Sie in **Beschreibung** eine Beschreibung für die Richtlinie ein.

6.  Geben Sie unter **Richtlinie für Organisatoren** in **Maximale Besprechungsgröße** die Höchstzahl an Benutzern ein, die für eine Besprechung zugelassen werden sollen. Der maximale Besprechungsumfang ist standardmäßig auf 250 festgelegt.

7.  Um Benutzer daran zu hindern, anonyme Benutzer zu Besprechungen einzuladen, deaktivieren Sie das Kontrollkästchen **Teilnehmer dürfen anonyme Benutzer einladen**. Anonyme Benutzer sind Benutzer, die über keine Anmeldeinformationen in Active Directory-Domänendienste Ihrer Organisation verfügen und daher nicht authentifiziert sind. In der Standardeinstellung können Benutzer anonyme Benutzer zu Besprechungen einladen.

8.  Führen Sie im Abschnitt **Aufzeichnung** eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Keine**, um Teilnehmer an der Aufzeichnung von Besprechungen zu hindern. Dies ist die Standardeinstellung.
    
      - Klicken Sie auf **Aufzeichnung aktivieren**, um Teilnehmern die Aufzeichnung von Besprechungen zu gestatten.

9.  Um externen Teilnehmern das Aufzeichnen von Besprechungen zu erlauben, aktivieren Sie das Kontrollkästchen **Partnerteilnehmern und anonymen Teilnehmern das Aufzeichnen gestatten**. In der Standardeinstellung werden externe Teilnehmer an der Aufzeichnung von Besprechungen gehindert.

10. Führen Sie im Abschnitt **Audio/Video** eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Keine**, um die Verwendung von Audio und Video zu verhindern.
    
      - Klicken Sie auf **IP-Audio aktivieren**, um die Verwendung von Audio, nicht jedoch von Video zuzulassen.
    
      - Klicken Sie auf **IP-Audio/Video aktivieren**, um die Verwendung von Audio und Video zuzulassen. Dies ist die Standardeinstellung.

11. Wenn Sie die Verwendung von Audio im Abschnitt **Audio/Video** zulassen, führen Sie eine der folgenden Aufgaben aus:
    
      - Wenn Sie Benutzer daran hindern möchten, per Einwahl an einer Besprechung teilzunehmen, deaktivieren Sie das Kontrollkästchen **PSTN-Einwahlkonferenzen aktivieren**. In der Standardeinstellung können Benutzer sich über das Festnetz (Public Switched Telephone Network, PSTN) in Besprechungen einwählen.
    
      - Wenn Sie Benutzern die Einwahl in Besprechungen gestatten und nicht authentifizierten (anonymen) Benutzern die Teilnahme an Besprechungen über eine ausgehende Telefonverbindung erlauben möchten, aktivieren Sie das Kontrollkästchen **Anonyme Teilnehmer dürfen ausgehende Verbindungen herstelle**. Bei ausgehenden Telefonverbindungen ruft der Konferenzserver den Benutzer an, und der Benutzer nimmt das Gespräch an, um an der Besprechung teilzunehmen. In der Standardeinstellung können anonyme Benutzer nicht über ausgehende Telefonverbindungen an Besprechungen teilnehmen.

12. Wenn Sie die Verwendung von Video im Abschnitt **Audio/Video** zulassen möchten, aktivieren Sie das Kontrollkästchen **Mehrere Videostreams zulassen**.

13. Führen Sie im Abschnitt **Datenzusammenarbeit** eine der folgenden Aktionen aus:
    
      - Wenn Sie keine Datenzusammenarbeit zulassen möchten, klicken Sie auf **Keine**.
    
      - Zum Zulassen einer Datenzusammenarbeit klicken Sie auf **Datenzusammenarbeit aktivieren**. Dies ist die Standardeinstellung.

14. Wenn Sie die Datenzusammenarbeit im Abschnitt **Datenzusammenarbeit** zulassen, führen Sie eine der folgenden Aufgaben aus:
    
      - Deaktivieren Sie das Kontrollkästchen **Partnerteilnehmer und anonyme Teilnehmer dürfen Inhalte herunterladen**. In der Standardeinstellung können externe Benutzer Inhalte herunterladen.
    
      - Deaktivieren Sie das Kontrollkästchen **Teilnehmer dürfen Dateien übertragen**, um Dateiübertragungen zu verhindern. In der Standardeinstellung können Dateien übertragen werden.
    
      - Deaktivieren Sie das Kontrollkästchen **Anmerkungen aktivieren**, um die Verwendung von Anmerkungen zu verhindern. Deaktivieren Sie das Kontrollkästchen **PowerPoint-Anmerkungen aktivieren**, um die Verwendung von Anmerkungen in freigegebenen PowerPoint-Präsentationen zu verhindern. In der Standardeinstellung sind Anmerkungen zulässig.
    
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

## So ändern Sie eine vorhandene Benutzer- oder Standortrichtlinie

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **Konferenzrichtlinie**.

4.  Klicken Sie in der Liste mit den Konferenzrichtlinien auf die Richtlinie, die Sie ändern möchten, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.

5.  Ändern Sie im Abschnitt **Konferenzrichtlinie bearbeiten** eine beliebige der Richtlinieneinstellungen. Hiervon ausgenommen ist der Richtlinienname, dieser kann nicht geändert werden.

6.  Klicken Sie auf **Commit ausführen**.


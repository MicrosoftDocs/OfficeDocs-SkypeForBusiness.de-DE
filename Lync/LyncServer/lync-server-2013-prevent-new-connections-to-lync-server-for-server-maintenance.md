---
title: Verhindern neuer Verbindungen mit Lync Server zur Serverwartung
TOCTitle: Verhindern neuer Verbindungen mit Lync Server zur Serverwartung
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520964(v=OCS.15)
ms:contentKeyID: 49293423
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verhindern neuer Verbindungen mit Lync Server zur Serverwartung

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Mit Lync Server können Sie einen Server offline schalten (um beispielsweise Software- oder Hardwareupgrades anzuwenden), ohne dass für die Benutzer eine Dienstunterbrechung entsteht.

Wenn Sie die Option zum Verhindern neuer Verbindungen oder Anrufe an einen Server innerhalb eines Pools angeben, werden keine neuen Verbindungen hergestellt oder Anrufe angenommen, sobald Sie diese Option aktivieren. Alle neuen Verbindungen und Anrufe werden an andere Server im Pool umgeleitet. Ein Server, der neue Verbindungen verhindert, ermöglicht die Fortsetzung von Sitzungen für bereits hergestellte Verbindungen, bis diese vom Benutzer beendet werden. Sobald alle vorhandenen Sitzungen beendet wurden, kann der Server offline geschaltet werden.

Wenn Sie neue Verbindungen mit einem Front-End-Server verhindern, hängen einige Lync Server-Funktionen und -Dienste zum Sicherstellen einer ordnungsgemäßen Funktionsweise vom DNS-Lastenausgleich ab. Wenn Sie keinen DNS-Lastenausgleich für den Pool verwenden, können Verbindungen über diese Dienste innerhalb des Zeitraums, in dem der Server neue Verbindungen verhindert, nicht an andere Server umgeleitet werden. Folglich kommt es für einige Sitzungen und Anrufe möglicherweise zu Unterbrechungen, wenn der Server offline geschaltet wird. Im Folgenden sind die Funktionen aufgeführt, die für eine ordnungsgemäße Funktionsweise dieser Option vom DNS-Lastenausgleich abhängen:

  - Vermittlung

  - Konferenzankündigungsanwendung

  - Reaktionsgruppenanwendung

  - Ansageanwendung

  - Anwendung zum Parken von Anrufen

Ausführliche Informationen zum DNS-Lastenausgleich finden Sie unter [DNS-Lastenausgleich in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in der Planungsdokumentation.

Sie können nicht nur neue Verbindungen für alle Dienste auf einem Server mit Lync Server, sondern auch neue Verbindungen für einzelne Lync Server-Dienste verhindern. Diese Methode ist z. B. nützlich, wenn Sie ein Lync Server-Update anwenden müssen, für das nicht der gesamte Server heruntergefahren werden muss. Hinweis: Wenn Sie Verbindungen für einen Dienst verhindern, müssen Sie den Dienst basierend auf der Gruppierung und Anzeige in der Windows-Liste von Diensten auswählen. Der Lync Server-Front-End-Dienst und der Datenerfassungs-Agent für die Überwachung sind z. B. separate Lync Server-Dienste, in der Windows-Liste von Diensten werden die beiden Dienste jedoch konsolidiert und als Lync Server-Front-End-Dienst angezeigt. Sie können neue Verbindungen für den Lync Server-Front-End-Dienst verhindern, es ist jedoch nicht möglich, neue Verbindungen für jeden der einzelnen zugrunde liegenden Lync Server-Dienste zu verhindern.


> [!IMPORTANT]
> Wenn Sie einen Server so konfigurieren, dass neue Verbindungen verhindert werden, und diesen Server anschließend neu starten, lässt der Server standardmäßig sofort wieder neue Verbindungen zu. Um dies zu verhindern, konfigurieren Sie den Server vor dem Neustart so, dass der Dienst nur manuell angehalten und fortgesetzt wird.



## So verhindern Sie neue Verbindungen mit Lync Server:

1.  Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.

2.  Öffnen Sie die Snap-In-Konsole "Dienste": Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und auf **Verwaltung**, und klicken Sie dann auf **Dienste**.

3.  Doppelklicken Sie in der Liste auf den Lync Server-Windows-Dienst, für den Sie neue Verbindungen verhindern möchten.

4.  Klicken Sie im Eigenschaftendialogfeld unter **Dienststatus: Gestartet** auf **Anhalten**.

5.  Es empfiehlt sich, neben **Starttyp** auf **Manuell** zu klicken. Dies ist jedoch optional.
    

    > [!IMPORTANT]
    > Wenn Sie einen Server so konfigurieren, dass neue Verbindungen verhindert werden, und diesen Server anschließend neu starten, lässt der Server standardmäßig sofort wieder neue Verbindungen zu. Um dies zu verhindern, konfigurieren Sie den Server vor dem Neustart so, dass der Dienst nur manuell angehalten und fortgesetzt wird.



6.  Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.


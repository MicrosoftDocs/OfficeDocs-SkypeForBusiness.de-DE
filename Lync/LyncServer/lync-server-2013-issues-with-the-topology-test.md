---
title: Probleme beim Topologietest
TOCTitle: Probleme beim Topologietest
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205045(v=OCS.15)
ms:contentKeyID: 49294592
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Probleme beim Topologietest

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Genau wie mit dem Cmdlet **Test-CsTopology** können Sie auch mit Best Practice Analyzer überprüfen, ob Lync Server 2013 auf globaler Ebene ordnungsgemäß funktioniert. Standardmäßig prüft Best Practice Analyzer, ebenso wie das Cmdlet, die gesamte Lync Server 2013-Infrastruktur. Dabei wird überprüft, ob die erforderlichen Dienste ausgeführt werden und die geeigneten Benutzerrechte und -berechtigungen für diese Dienste und die beim Installieren von Lync Server 2013 erstellten universellen Sicherheitsgruppen festgelegt sind.

Neben der Überprüfung der Gültigkeit der gesamten Lync Server-Topologie, können Sie mit **Test-CsTopology** die Gültigkeit eines spezifischen Diensts prüfen. Ausführliche Informationen zur Verwendung des Cmdlets zum Testen bestimmter Dienste finden Sie unter [Test-CsTopology](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTopology) in der Lync Server-Verwaltungsshell-Dokumentation. Nutzen Sie die folgenden Informationen, um Probleme mit Ihrer Topologie zu lösen.


> [!NOTE]
> Je nach Konfiguration Ihrer Edgeserver und den entsprechenden Einstellungen im Umkreisnetzwerk, inklusive Firewall- Einstellungen und Berechtigungen, kann Best Practices Analyzer möglicherweise nicht auf Ihre Edgeserver zugreifen, um diese zu scannen. Wenn Sie die Edgeserver scannen lassen und die Berichte anzeigen, dass ein Zugriffsproblem für die Edgeserver vorliegt, deaktivieren Sie das Kontrollkästchen <STRONG>Edgeserver</STRONG>, und führen Sie den Scanvorgang erneut aus, um zu verhindern, dass das Problem in den Berichten aufgelistet wird.



## Problembehebung für Ihre Topologie

Wenn beim Topologietest Probleme mit Ihrer Topologie gefunden werden, werden diese Probleme wahrscheinlich durch Fehler verursacht, die beim Veröffentlichen oder Aktivieren Ihrer Topologie aufgetreten sind.

Wenn Sie Änderungen an Ihrer Topologie vornehmen, werden die Änderungen erst dann wirksam, wenn sie sowohl veröffentlicht als auch aktiviert wurden. Verwenden Sie unbedingt das Topologie-Generator, um Änderungen an Ihrer Topologie vorzunehmen. Nachdem Sie die Änderungen vorgenommen haben, können Sie diese Änderungen mit dem Topologie-Generator veröffentlichen und aktivieren.

Wenn Sie die Änderungen veröffentlichen, werden die neuen Informationen (z. B. ein neuer Standort oder eine neue Serverrolle) in den zentralen Verwaltungsspeicher geschrieben. Diese neuen (oder geänderten) Objekte werden jedoch nicht sofort in Ihre Topologie aufgenommen. Objekte werden erst dann in Ihre Topologie aufgenommen, wenn Sie die aktualisierte Topologie aktivieren. Wenn Sie im Topologie-Generator die Option zum Veröffentlichen wählen, werden beide Schritte ausgeführt – die Änderungen werden veröffentlicht (bzw. in den zentralen Verwaltungsspeicher geschrieben), und dann wird die neue Topologie aktiviert.

Standardmäßig sind Mitglieder der Gruppe "RTCUniversalServerAdmins" autorisiert, die Cmdlets **Publish-CsTopology** und **Enable-CsTopology** auszuführen. Wenn die Setupberechtigungen jedoch nicht delegiert wurden, müssen Sie als Domänenadministrator angemeldet sein, um das Cmdlet **Publish-CsTopology** auszuführen. Damit RTCUniversalServerAdmins die Berechtigung erhalten, das Cmdlet **Publish-CsTopology** zu verwenden, müssen Sie das Cmdlet **Grant-CsSetupPermission** für jeden Active Directory-Container ausführen, der Computer enthält, auf denen Lync Server-Dienste ausgeführt werden. Damit RTCUniversalServerAdmins die Berechtigung erhalten, das Cmdlet **Enable-CsTopology** auszuführen, müssen Sie das Cmdlet **Set-CsSetupPermission** für jeden Active Directory-Container ausführen, der Computer enthält, auf denen Lync Server-Dienste ausgeführt werden. Beachten Sie, dass dies für die Aktivierung und Veröffentlichung einer Topologie mit dem Topologie-Generator gilt. Wenn Sie die Berechtigungen nicht mit **Set-CsSetupPermission** delegiert haben, kann nur ein Domänenadministrator eine Topologie mit dem Topologie-Generator aktivieren und veröffentlichen.


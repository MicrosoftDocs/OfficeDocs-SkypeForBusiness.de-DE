---
title: Anwenden einer Lync Server-Archivierungsrichtlinie auf einen Benutzer
TOCTitle: Anwenden einer Lync Server-Archivierungsrichtlinie auf einen Benutzer
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205143(v=OCS.15)
ms:contentKeyID: 49294950
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anwenden einer Lync Server-Archivierungsrichtlinie auf einen Benutzer

 

_**Letztes Änderungsdatum des Themas:** 2012-10-10_

Nach dem Erstellen einer Lync Server-Benutzerrichtlinie müssen Sie sie auf die jeweiligen Benutzer oder Benutzergruppen anwenden, die in Lync Server 2013 verwaltet werden, bevor die Benutzerrichtlinie wirksam werden kann. Einzelheiten zum Erstellen von Benutzerrichtlinien für spezielle Benutzer finden Sie unter [Erstellen und Konfigurieren von Benutzerrichtlinien für die Archivierung in Lync Server](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) in der Bereitstellungsdokumentation.

Einzelheiten zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für globale, Standort- und Benutzerrichtlinien, finden Sie unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder Betriebsdokumentation.


> [!NOTE]
> Damit Sie die Archivierung konfigurieren und verwenden können, müssen Sie sie zunächst bereitstellen. Ausführliche Informationen hierzu finden Sie in der Bereitstellungsdokumentation unter <A href="lync-server-2013-deploying-archiving.md">Bereitstellen der Archivierung in Lync Server 2013</A>.<BR>Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktiviert haben, wird mithilfe von Compliance-Archivrichtlinien in Exchange festgelegt, ob die Archivierung für die Benutzer aktiviert wird, die in Exchange 2013 verwaltet werden und die ihre Postfächer in Compliance-Archive verschoben haben. Einzelheiten dazu finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung beim Verwenden von Exchange Server-Integration</A> in der Bereitstellungsdokumentation.<BR>Vor dem Aktivieren der Archivierung sollten Sie alle entsprechenden Optionen in den Archivierungskonfigurationen angeben. Ausführliche Informationen hierzu finden Sie unter <A href="lync-server-2013-configuring-archiving-options.md">Konfigurieren von Archivierungsoptionen</A> in der Bereitstellungsdokumentation.



## So wenden Sie eine Lync Server-Archivierungsrichtlinie auf einen Benutzer an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um Systemsteuerung für Lync Server 2013 zu öffnen. Einzelheiten zu den verschiedenen Methoden, die Sie zum Starten der Systemsteuerung für Lync Server 2013 verwenden können, finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.

4.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

5.  Wählen Sie für **Lync Server-Benutzer bearbeiten** unter **Archivierungsrichtlinie** die anzuwendende Richtlinie zur Benutzerarchivierung aus.
    

    > [!NOTE]
    > Mit den Einstellungen <STRONG>&lt;Automatisch&gt;</STRONG> werden die Standardeinstellungen der Serverinstallation angewendet. Diese Einstellungen werden vom Server automatisch übernommen.



6.  Klicken Sie auf **Commit**.


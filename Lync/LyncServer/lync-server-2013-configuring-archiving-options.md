---
title: Konfigurieren von Archivierungsoptionen
TOCTitle: Konfigurieren von Archivierungsoptionen
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205182(v=OCS.15)
ms:contentKeyID: 49295135
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Archivierungsoptionen

 

_**Letztes Änderungsdatum des Themas:** 2012-10-10_

In der Systemsteuerung für Lync Server 2013 verwenden Sie Archivierungskonfigurationen, um anzugeben, wie die Archivierung implementiert wird. Dies beinhaltet die folgenden Archivierungskonfigurationen:

  - Eine globale Konfiguration, die standardmäßig erstellt wird, wenn Sie Lync Server 2013 bereitstellen.

  - Optionale Konfigurationen auf Standortebene und Poolebene, die Sie erstellen und Verwenden können, um anzugeben, wie die Archivierung für bestimmte Standorte oder Pools implementiert wird.

Sie legen Archivierungskonfigurationen anfangs fest, wenn Sie Archivierungen bereitstellen, Sie können jedoch nach der Bereitstellung Konfigurationen ändern, hinzufügen und löschen. In der Systemsteuerung für Lync Server 2013 können Sie die Seite **Archivierungskonfiguration** der Gruppe **Archivierung und Überwachung** verwenden, um Konfigurationen auf globaler Ebene, auf Standort- und auf Poolebene zu verwalten. Details über das Implementieren von Archivierungskonfigurationen, einschließlich der von Ihnen anzugebenden Optionen und der Hierarchie von Archivierungskonfigurationen, finden Sie unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder Betriebsdokumentation. Details zum Verwalten von Konfigurationen nach der Bereitstellung finden Sie unter [Verwalten von Konfigurationsoptionen für die Archivierung in Lync Server 2013 für Ihre Organisation, Standorte und Pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in der Betriebsdokumentation.


> [!NOTE]
> Zum Verwenden der Archivierung müssen Sie Archivierungsrichtlinien konfigurieren, um anzugeben, ob die Archivierung für interne oder externe Kommunikationen oder für beide für auf Lync Server 2013 verwaltete Benutzer aktiviert werden soll. Standardmäßig ist die Archivierung weder für interne noch für externe Kommunikationen aktiviert. Vor dem Aktivieren der Archivierung in sämtlichen Richtlinien sollten Sie die entsprechenden Archivierungskonfigurationen für Ihre Bereitstellung und optional für bestimmte Standorte und Pools angeben, wie dies in diesem Abschnitt beschrieben wird. Details zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien</A> in der Bereitstellungsdokumentation.<BR>Wenn Sie die Microsoft Exchange-Integration nicht für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie Archivierungsrichtlinien konfigurieren, um anzugeben, ob die Archivierung für interne oder externe Kommunikationen oder für beide aktiviert werden soll. Standardmäßig ist die Archivierung weder für interne noch für externe Kommunikationen für das Archivieren von Daten aktiviert, wenn Lync Server 2013-Archivierungsdatenbanken verwendet werden. Vor dem Aktivieren der Archivierung in sämtlichen Richtlinien sollten Sie die entsprechenden Archivierungskonfigurationen für Ihre Bereitstellungen und optional für bestimmte Standorte und Pools angeben, wie dies in diesem Abschnitt beschrieben ist. Details zum Aktivieren der Archivierung für die Verwendung mit Lync Server 2013-Archivierungsdatenbanken finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien</A> in der Bereitstellungsdokumentation.



## In diesem Abschnitt

  - [Konfigurieren von Archivierungsoptionen auf globaler Ebene](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [Konfigurieren von Archivierungsoptionen für einen Standort](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [Konfigurieren von Archivierungsoptionen für einen Pool](lync-server-2013-configuring-archiving-options-for-a-pool.md)


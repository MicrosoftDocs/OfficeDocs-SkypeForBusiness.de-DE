---
title: 'Lync Server 2013: Vorbereiten gesperrter Active Directory-Domänendienste'
TOCTitle: Vorbereiten gesperrter Active Directory-Domänendienste
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398492(v=OCS.15)
ms:contentKeyID: 49294277
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vorbereiten gesperrter Active Directory-Domänendienste in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-05-14_

Organisationen sperren die Active Directory-Domänendienste häufig, um Sicherheitsrisiken zu mindern. Durch das Sperren einer Active Directory-Umgebung können jedoch die Berechtigungen beschränkt werden, die für Lync Server 2013 erforderlich sind. Die ordnungsgemäße Vorbereitung einer gesperrten Active Directory-Umgebung für Lync Server 2013 erfordert einige zusätzliche Überlegungen und Schritte.

Zwei Möglichkeiten, wie Berechtigungen in einer gesperrten Active Directory-Umgebung beschränkt sein können, sind:

  - Zugriffssteuerungseinträge (Access Control Entries, ACEs) authentifizierter Benutzer wurden aus den Containern entfernt.

  - Die Vererbung von Berechtigungen wurde für Container mit Benutzer-, Kontakt-, InetOrgPerson- oder Computerobjekten deaktiviert.

## In diesem Abschnitt

  - [Entfernte Berechtigungen für authentifizierte Benutzer in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [Vererbung von Berechtigungen ist für Computer-, Benutzer- oder InetOrgPerson-Container deaktiviert in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)


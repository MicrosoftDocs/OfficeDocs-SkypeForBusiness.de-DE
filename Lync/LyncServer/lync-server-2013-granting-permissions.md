---
title: 'Lync Server 2013: Gewähren von Berechtigungen'
TOCTitle: Gewähren von Berechtigungen
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398901(v=OCS.15)
ms:contentKeyID: 49295486
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gewähren von Berechtigungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-15_

Zum Setup können Sie der universellen Gruppe RTCUniversalServerAdmins Berechtigungen für eine spezifische Active Directory-Organisationseinheit gewähren, sodass Mitglieder dieser Gruppe in dieser Organisationseinheit Lync Server 2013 in der angegebenen Domäne installieren können. Sie können folgende Berechtigungen gewähren:

  - Lesen

  - Schreiben

  - ReadSPN

  - WriteSPN

Zur Verwaltung können Sie bestimmten Organisationseinheiten Berechtigungen gewähren, sodass Mitglieder der während der Gesamtstrukturvorbereitung erstellten universellen RTC-Gruppen auf die Organisationseinheit zugreifen können, ohne Mitglieder der Gruppe "Domänen-Admins" zu sein. Bei den Berechtigungen, die Sie zur angegebenen Organisationseinheit hinzufügen, handelt es sich um die gleichen Berechtigungen, die das Cmdlet **Enable-CsAdDomain** den OU-Containern für Computer und Benutzer hinzufügt.

## In diesem Abschnitt

  - [Gewähren von Setupberechtigungen in Lync Server 2013](lync-server-2013-granting-setup-permissions.md)

  - [Gewähren von Berechtigungen für die Organisationseinheit in Lync Server 2013](lync-server-2013-granting-organizational-unit-permissions.md)


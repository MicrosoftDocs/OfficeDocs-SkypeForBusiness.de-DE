---
title: Anzeigen einer Liste vertrauenswürdiger Anwendungen
TOCTitle: Anzeigen einer Liste vertrauenswürdiger Anwendungen
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182604(v=OCS.15)
ms:contentKeyID: 49295852
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen einer Liste vertrauenswürdiger Anwendungen

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Sie können mithilfe der Systemsteuerung für Lync Server 2013 eine Liste der vertrauenswürdigen Anwendungen anzeigen, die in Ihrer Lync Server 2013-Umgebung bereitgestellt wurden. Eine vertrauenswürdige Anwendung ist eine auf dem Microsoft UCMA (Unified Communications Managed API) 3.0 Core SDK basierende Anwendung, die von Lync Server 2013 als vertrauenswürdig eingestuft wird. Die Eigenschaften dieser Vertrauensbeziehung werden in der folgenden Liste zusammengefasst:

  - Für vertrauenswürdige Anwendungen wird von Lync Server keine Authentifizierung angefordert.

  - Vertrauenswürdige Anwendungen werden von Lync Server weder für SIP-Transaktionen noch für Verbindungen oder ausgehende VoIP-Anrufe (Voice over Internet) gedrosselt.

  - Vertrauenswürdige Anwendungen können die Identität beliebiger Benutzer annehmen und Konferenzen beitreten, ohne in Konferenzlisten aufzutauchen.

  - Vertrauenswürdige Anwendungen sind hochverfügbar und ausfallsicher.

In der Lync Server-Systemsteuerung können Sie den Namen der Anwendungen, den Pool für deren Ausführung sowie den verwendeten Port für die Anwendungen anzeigen.

## So zeigen Sie eine Liste der vertrauenswürdigen Anwendungen an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsServerAdministrator", "CsAdministrator", "CsHelpDesk" oder "CsViewOnlyAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. Informationen zu den verfügbaren vordefinierten Administratorrollen in Lync Server 2013 finden Sie unter [Planen für die rollenbasierte Zugriffssteuerung in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Vertrauenswürdige Anwendung**.

4.  Klicken Sie auf der Seite **Vertrauenswürdige Anwendung** auf eine Spaltenüberschrift, um die Anwendungen bei Bedarf zu sortieren.

## Siehe auch

#### Weitere Ressourcen

[Verwalten der Lync Server 2013-Topologie](lync-server-2013-managing-the-lync-server-topology.md)


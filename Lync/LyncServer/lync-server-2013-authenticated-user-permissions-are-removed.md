---
title: 'Lync Server 2013: Entfernte Berechtigungen für authentifizierte Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d5e14b8129f771093ed9facb09d047ac7c36d32
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a>Entfernte Berechtigungen für authentifizierte Benutzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

In einer gesperrten Active Directory-Umgebung werden authentifizierte Benutzerzugriffs Steuerungs Einträge (ACEs) aus den standardmäßigen Active Directory-Containern, einschließlich der Benutzer, der Konfiguration oder des Systems, und der Organisationseinheiten entfernt, in denen Benutzer und Computer Objekte werden gespeichert. Durch das Entfernen von authentifizierten Benutzer-ACEs wird der Lesezugriff auf Active Directory-Informationen verhindert. Das Entfernen der ACEs führt jedoch zu Problemen bei lync Server 2013, da diese von Leseberechtigungen für diese Container abhängen, damit Benutzer die Domänenvorbereitung ausführen können.

In diesem Fall gewährt die Mitgliedschaft in der Gruppe der Domänenadministratoren, die für die Ausführung der Domänenvorbereitung, Serveraktivierung und Poolerstellung erforderlich ist, keinen Lesezugriff mehr auf Active Directory-Informationen, die in den Standardcontainern gespeichert sind. Sie müssen manuell Lesezugriffsberechtigungen für verschiedene Container in der Stammdomäne der Gesamtstruktur erteilen, um zu überprüfen, ob die Vorbereitungs Prozedur für die erforderliche Gesamtstruktur abgeschlossen ist.

Damit ein Benutzerdomänen Vorbereitung, Serveraktivierung oder Poolerstellung für eine beliebige Stammdomäne ohne Gesamtstruktur ausführen kann, haben Sie die folgenden Optionen:

  - Verwenden Sie ein Konto, das ein Mitglied der Gruppe "Organisations-Admins" ist, um die Domänenvorbereitung auszuführen.

  - Verwenden Sie ein Konto, das ein Mitglied der Gruppe der Domänenadministratoren ist, und weisen Sie diesem Konto Lesezugriffsberechtigungen für jeden der folgenden Container in der Gesamtstruktur-Stammdomäne zu:
    
      - Domäne
    
      - Konfiguration oder System

Wenn Sie kein Konto verwenden möchten, das ein Mitglied der Gruppe "Organisations-Admins" ist, um die Domänenvorbereitung oder andere Setup Aufgaben auszuführen, geben Sie dem Konto, für das Sie Lesezugriff verwenden möchten, explizit die entsprechenden Container im Gesamtstrukturstamm.

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a>So erteilen Sie Benutzern Lesezugriffsberechtigungen für Container in der Stammdomäne der Gesamtstruktur

1.  Melden Sie sich bei dem Computer an, der der Gesamtstruktur-Stammdomäne mit einem Konto zugeordnet ist, das ein Mitglied der Gruppe "Domänen-Admins" für die Gesamtstruktur-Stammdomäne ist.

2.  Führen Sie adsiedit. msc für die Gesamtstruktur-Stammdomäne aus.
    
    Wenn authentifizierte Benutzer-ACEs aus dem Domänen-, Konfigurations-oder System Container entfernt wurden, müssen Sie dem Container schreibgeschützte Berechtigungen erteilen, wie in den folgenden Schritten beschrieben.

3.  Klicken Sie mit der rechten Maustaste auf den Container, und klicken Sie dann auf **Eigenschaften**.

4.  Klicken Sie auf die Registerkarte **Sicherheit** .

5.  Klicken Sie auf **Erweitert**.

6.  Klicken Sie auf der Registerkarte **Berechtigungen** auf **Hinzufügen**.

7.  Geben Sie den Namen des Benutzers oder der Gruppe ein, der Berechtigungen erhält, indem `domain\account name`Sie folgendes Format verwenden:, und klicken Sie dann auf **OK**.

8.  Klicken Sie auf der Registerkarte **Objekte** unter **gilt für**auf **nur dieses Objekt**.

9.  Wählen Sie unter **Berechtigungen**die folgenden ACEs zulassen aus, indem Sie auf die Spalte **zulassen** klicken: **Inhalt**auflisten, **alle Eigenschaften lesen**und **Berechtigungen Lesen**.

10. Klicken Sie zweimal auf **OK** .

11. Wiederholen Sie diese Schritte für alle relevanten Container, die in Schritt 2 aufgeführt sind.

</div>

</div>

<span> </span>

</div>

</div>

</div>


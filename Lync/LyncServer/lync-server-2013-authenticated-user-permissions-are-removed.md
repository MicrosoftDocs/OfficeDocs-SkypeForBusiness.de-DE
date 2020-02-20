---
title: 'Lync Server 2013: authentifizierte Benutzerberechtigungen werden entfernt'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45080baa0839731808aefcc31c1551bfab5293db
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a>Berechtigungen für authentifizierte Benutzer werden in lync Server 2013 entfernt.

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

In einer gesperrten Active Directory Umgebung werden authentifizierte Benutzerzugriffs Steuerungs Einträge (ACEs) aus den standardmäßigen Active Directory Containern entfernt, einschließlich der Benutzer, der Konfiguration oder des Systems sowie der Organisationseinheiten (Organizational Units, OUs), in denen Benutzer und Computer Objekte werden gespeichert. Durch das Entfernen authentifizierter Benutzer-ACEs wird der Lesezugriff auf Active Directory Informationen verhindert. Das Entfernen der ACEs verursacht jedoch Probleme für lync Server 2013, da Sie von Leseberechtigungen für diese Container abhängt, damit Benutzer die Domänenvorbereitung ausführen können.

In diesem Fall erteilt die Mitgliedschaft in der Gruppe "Domänen-Admins", die zum Ausführen der Domänenvorbereitung, Serveraktivierung und Poolerstellung erforderlich ist, keinen Lesezugriff mehr auf Active Directory Informationen, die in den Standardcontainern gespeichert sind. Sie müssen Lesezugriff-Berechtigungen für verschiedene Container in der Gesamtstruktur-Stammdomäne manuell erteilen, um zu überprüfen, ob die Vorbereitungs Prozedur für die erforderliche Gesamtstruktur abgeschlossen ist.

Um einem Benutzer die Ausführung der Domänenvorbereitung, Serveraktivierung oder Poolerstellung in einer nicht-Gesamtstruktur-Stammdomäne zu ermöglichen, haben Sie die folgenden Optionen:

  - Verwenden Sie ein Konto, das Mitglied der Gruppe "Organisations-Admins" ist, um die Domänenvorbereitung auszuführen.

  - Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" ist, und erteilen Sie diesem Konto Lesezugriffsberechtigungen für jeden der folgenden Container in der Gesamtstruktur-Stammdomäne:
    
      - Domäne
    
      - Konfiguration oder System

Wenn Sie ein Konto, das Mitglied der Gruppe "Organisations-Admins" ist, zum Ausführen der Domänenvorbereitung oder anderer Setup Aufgaben nicht verwenden möchten, erteilen Sie dem Konto, für das Sie den Lesezugriff verwenden möchten, explizit die entsprechenden Container im Gesamtstrukturstamm.

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a>So erteilen Sie Benutzern Lesezugriffsberechtigungen für Container in der Gesamtstruktur-Stammdomäne

1.  Melden Sie sich bei dem Computer, der der Gesamtstruktur-Stammdomäne angehört, mit einem Konto an, das Mitglied der Gruppe "Domänen-Admins" für die Gesamtstruktur-Stammdomäne ist.

2.  Führen Sie adsiedit. msc für die Gesamtstruktur-Stammdomäne aus.
    
    Wenn authentifizierte Benutzer-ACEs aus der Domäne, Konfiguration oder dem System Container entfernt wurden, müssen Sie dem Container schreibgeschützte Berechtigungen erteilen, wie in den folgenden Schritten beschrieben.

3.  Klicken Sie mit der rechten Maustaste auf den Container, und klicken Sie dann auf **Eigenschaften**.

4.  Klicken Sie auf die Registerkarte **Sicherheit**.

5.  Klicken Sie auf **Erweitert**.

6.  Klicken Sie auf der Registerkarte **Berechtigungen** auf **Hinzufügen**.

7.  Geben Sie den Namen des Benutzers oder der Gruppe ein, der Berechtigungen erhält, indem `domain\account name`Sie folgendes Format verwenden:, und klicken Sie dann auf **OK**.

8.  Klicken Sie auf der Registerkarte **Objekte** unter **gilt für**auf **nur dieses Objekt**.

9.  Wählen Sie unter **Berechtigungen**die folgenden ACEs zulassen aus, indem Sie auf die Spalte **zulassen** klicken: **Inhalt auflisten**, **alle Eigenschaften lesen**und **Berechtigungen Lesen**.

10. Klicken Sie zweimal auf **OK**.

11. Wiederholen Sie diese Schritte für alle in Schritt 2 aufgeführten relevanten Container.

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Konfigurieren von Einwahlnummern für Einwahlkonferenzen'
TOCTitle: 'Konfigurieren von Einwahlnummern für Einwahlkonferenzen '
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398952(v=OCS.15)
ms:contentKeyID: 49295578
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Einwahlnummern für Einwahlkonferenzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2011-07-17_

Beim Bereitstellen von Einwahlkonferenzen müssen Sie Telefonnummern einrichten, die Benutzer aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) wählen können, um am Audioteil einer Konferenz teilzunehmen. Diese Zugriffsnummern für die Einwahl werden in Besprechungseinladungen und auf der Webseite mit den Einstellungen für Einwahlkonferenzen angezeigt.

Vor dem Erstellen von Zugriffsnummern für die Einwahl müssen Sie zunächst die Regionen Ihrer Einwahlkonferenzen planen und anschließend Wählpläne für die Regionen konfigurieren. Ausführliche Informationen zu Regionen finden Sie unter [Anforderungen für Einwahlkonferenzen in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in der Planungsdokumentation. Ausführliche Informationen zum Konfigurieren von Wählplänen für Einwahlkonferenzen finden Sie unter [Konfigurieren von Wählplänen für Einwahlkonferenzen in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).


> [!NOTE]
> Sie können eine neue Zugriffsnummer erst dann für Einwahlkonferenzen verwenden, wenn die Replikation der Active Directory-Domänendienste (AD&nbsp;DS) für diese Zugriffsnummer abgeschlossen ist. Die Replikation kann mehrere Stunden in Anspruch nehmen.




> [!NOTE]
> Nach dem Erstellen von Zugriffsnummern für die Einwahl können Sie den Anzeigenamen für die Active Directory-Kontaktobjekte modifizieren, sodass Benutzer die richtige Zugriffsnummer einfacher identifizieren können. Verwenden Sie das Cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG>, um den Anzeigenamen zu ändern. Active Directory-Objekte sollten nicht manuell geändert werden. Ausführliche Informationen zum Ändern einer Zugriffsnummer finden Sie in der Lync Server-Verwaltungsshell-Dokumentation zum Cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG>.



## In diesem Abschnitt

[Erstellen oder Ändern einer Einwahlnummer für Einwahlkonferenzen in Lync Server 2013](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

## Siehe auch

#### Konzepte

[Anforderungen für Einwahlkonferenzen in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)  

#### Weitere Ressourcen

[Konfigurieren von Wählplänen für Einwahlkonferenzen in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)


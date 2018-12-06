---
title: 'Lync Server 2013: Bereitstellen des einheitlichen Kontaktspeichers'
TOCTitle: Bereitstellen des einheitlichen Kontaktspeichers
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204963(v=OCS.15)
ms:contentKeyID: 49294274
ms.date: 06/06/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen des einheitlichen Kontaktspeichers in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-06-06_

Zum Aktivieren des einheitlichen Kontaktspeichers in Lync Server 2013 sind keine Topologieeinstellungen erforderlich. Wenn Sie den Kontaktspeicher für Benutzer aktivieren möchten, müssen Sie die folgenden Punkte sicherstellen:

  - Die Richtlinie für den einheitlichen Kontaktspeicher muss aktiviert sein (was in der Standardeinstellung der Fall ist).

  - Die Benutzer müssen sich bei Lync 2013 mindestens einmal anmelden.

Nachdem die Kontakte eines Benutzers migriert wurden (was automatisch erfolgt, wenn sich der Benutzer bei Lync 2013 anmeldet), kann der Benutzer auf seine Lync-Kontakte über Lync 2013, Outlook 2013 oder Outlook Web Access zugreifen und diese verwalten. Er muss nicht bei Lync angemeldet sein, um seine Kontakte von Outlook oder Outlook Web Access aus zu verwalten.


> [!IMPORTANT]
> Wenn sich ein Benutzer nach der Migration das nächste Mal in Lync 2010 anmeldet, sind seine Kontakte und Gruppen verfügbar und auf dem aktuellen Stand, der Benutzer kann sie jedoch nicht verwalten (d.&nbsp;h. hinzufügen, löschen, verschieben, kennzeichnen, Kennzeichnungen aufheben oder ändern).



## In diesem Abschnitt

  - [Aktivieren von Benutzern für den einheitlichen Kontaktspeicher in Lync Server 2013](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [Migrieren von Benutzern zum einheitlichen Kontaktspeicher in Lync Server 2013](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [Zurücksetzen von migrierten Benutzern in Lync Server 2013](lync-server-2013-roll-back-migrated-users.md)


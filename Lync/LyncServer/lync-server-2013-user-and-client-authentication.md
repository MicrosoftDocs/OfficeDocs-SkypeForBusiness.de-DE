---
title: Benutzer- und Clientauthentifizierung für Lync Server 2013
TOCTitle: Benutzer- und Clientauthentifizierung für Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59679134
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Benutzer- und Clientauthentifizierung für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-11-11_

Ein vertrauenswürdiger Benutzer ist ein Benutzer, der von einem vertrauenswürdigen Server in Microsoft Lync Server 2013 authentifiziert wurde. Dieser Server für gewöhnlich ein Standard Edition-Server, Enterprise EditionFront-End-Server oder Director. Lync Server 2013 nutzt Active Directory-Domänendienste als einziges vertrauenswürdiges Back-End-Repository für Benutzeranmeldeinformationen.

Authentifizierung bedeutet die Bereitstellung von Benutzeranmeldeinformationen an einen vertrauenswürdigen Server. Lync Server 2013 verwendet die folgenden Authentifizierungsprotokolle, abhängig vom Status und Standort des Benutzers.

  - **MIT Kerberos Version 5-Sicherheitsprotokoll** für interne Benutzer mit Active Directory-Anmeldeinformationen. Kerberos erfordert eine Clientverbindung mit Active Directory-Domänendienste und kann deshalb nicht für die Authentifizierung von Clients außerhalb der Firewall des Unternehmens verwendet werden.

  - **NTLM-Protokoll** für Benutzer mit Active Directory-Anmeldeinformationen, die sich von einem Endpunkt außerhalb der Unternehmensfirewall verbinden. Der Zugriffs-Edgedienst leitet Anmeldeanforderungen an einen Director, falls vorhanden, oder einen Front-End-Server zur Authentifizierung weiter. Der Zugriffs-Edgedienst selbst führt keine Authentifizierung durch.
    

    > [!NOTE]
    > Da der Angriffsschutz des NTLM-Protokolls schwächer ist als der von Kerberos, minimieren einige Unternehmen die Nutzung von NTLM. Deshalb ist der Zugriff auf Lync Server 2013 möglicherweise auf interne oder über eine VPN- oder DirectAccess-Verbindung verbundene Clients beschränkt.



  - **Das Digest-Protokoll** für sogenannte anonyme Benutzer. Anonyme Benutzer sind außenstehende Benutzer, die keine anerkannten Active Directory-Anmeldeinformationen haben, aber zu einer lokalen Konferenz eingeladen wurden und einen gültigen Konferenzschlüssel besitzen. Die Digest-Authentifizierung wird nicht für andere Clientinteraktionen verwendet.

Die Lync Server 2013-Authentifizierung umfasst zwei Phasen:

1.  Zwischen dem Client und dem Server wird eine Sicherheitszuordnung eingerichtet.

2.  Client und Server verwenden die vorhandene Sicherheitszuordnung, um Nachrichten, die sie senden, zu signieren, und Nachrichten, die sie empfangen, zu prüfen. Nicht authentifizierte Nachrichten von einem Client werden nicht akzeptiert, wenn die Authentifizierung auf dem Server aktiviert ist.

Die Benutzervertrauenswürdigkeit ist mit jeder Nachricht verbunden, die von einem Benutzer stammt, nicht der Benutzeridentität an sich. Der Server überprüft jede Nachricht auf gültige Benutzeranmeldeinformationen. Wenn die Benutzeranmeldeinformationen gültig sind, bleibt die Nachricht unbehelligt, nicht nur vom ersten Server, der sie empfängt, sondern von allen anderen Servern in der vertrauenswürdigen Servercloud.

Benutzer mit gültigen Anmeldedaten, die von einem Verbundpartner ausgegeben wurden, sind vertrauenswürdig, werden aber optional durch zusätzliche Einschränkungen davon abgehalten, die vollständige Reihe von Berechtigungen zu erhalten, die internen Benutzern gewährt werden.

Die Protokolle ICE und TURN verwenden ebenfalls die Digest-Abfrage, wie im IETF TURN RFC beschrieben.

Clientzertifikate bieten eine alternative Möglichkeit für die Authentifizierung von Benutzern durch Lync Server 2013. Statt einen Benutzernamen und ein Kennwort bereitzustellen, haben Benutzer ein Zertifikat und den privaten Schlüssel, der dem Zertifikat entspricht und der erforderlich ist, um eine kryptografische Anfrage aufzulösen. (Dieses Zertifikat muss einen Antragstellernamen oder einen alternativen Antragstellernamen haben, mit dem der Benutzer identifiziert wird und der von einer Stammzertifizierungsstelle ausgestellt sein muss, die für die Server vertrauenswürdig ist, auf denen Lync Server 2013 ausgeführt wird. Das Zertifikat muss sich außerdem in seinem Gültigkeitszeitraum befinden und darf nicht gesperrt sein.) Zur Authentifizierung müssen Benutzer nur eine persönliche Identifikationsnummer (PIN) eingeben. Zertifikate sind insbesondere für Telefone und andere Geräte nützlich, auf denen Microsoft Lync 2013 Phone Edition ausgeführt und bei denen die Eingabe eines Benutzernamens und/oder Kennworts schwierig ist.


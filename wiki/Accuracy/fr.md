Précision
==========

Il y a 3 types de précision : La précision par [beatmap](/wiki/Beatmaps), la précision globale personnelle et la précision des [pp](/wiki/Performance_Points).

En bref, la précision de la beatmap dépend du [Score](/wiki/Score) obtenu, la précision globale dépend de la précision de chaque meilleur score sur une beatmap (veuillez noter que la précision est pondérée d'une certaine manière afin que les scores à forte précision influencent plus que les scores à faible précision), et la précision des pp dépend des scores en ligne sur les beatmaps éligibles au gain de pp.

osu!
---------------

En mode [osu!](/wiki/Game_Modes/osu!), la précision en pourcentage est calculée en mesurant le score obtenu de chaque note et en le divisant par le montant maximal possible. En d'autres termes :

**Précision = Total des points des notes / (Nombre de notes * 300)**

| Total des points des notes | Nombre de notes |
| ---------------------------| ----------------|
| (Nombre de 50* 50 + Nombre de 100 * 100 + Nombre de 300 * 300) | (Nombre de ratés + Nombre de 50 + Nombre de 100 + Nombre de 300) |

Pour référence: 300 = 6/6, 100 = 2/6, 50 = 1/6, Raté = 0/6.

osu!taiko
-----------

En mode [osu!taiko](/wiki/Game_Modes/osu!taiko), la précision de la chanson est calculée en additionnant la précision de chaque note puis en la divisant par le nombre total de notes. Un EXCELLENT (良) vaut 100%, un BIEN (可) vaut 50% et un RATÉ/MAUVAIS (不可) vaut 0%. Les drumrolls et spinners n'influencent pas la précision.

**Précision = Total des points des notes / (Nombre de notes * 300)**

| Total des points des notes | Nombre de notes |
| ---------------------------| --------------- |
| (Nombre de Ratés * 0 + Nombre de 100(BIEN) * 0.5 + Nombre de 300(EXCELLENT) * 1) * 300 | (Nombre de Ratés + Nombre de 100 + Nombre de 300) |

osu!catch
---------------------

En mode [osu!catch](/wiki/Game_Modes/osu!catch), la précision de la chanson est calculée en additionnant les objets collectés hormis les spinners puis divisé par le nombre total d'objets hors spinners.

**Précision = Nombre de fruits attrapés / Nombre de fruits total**

| Nombre de fruits attrapés | Nombre de fruits total | Condition |
| --------------------------| ---------------------- | --------- |
| (Nombre de droplets + Nombre de 100s + Nombre de 300s) | (Nombre de Ratés + Nombre de droplets + Nombre de 100s + Nombre de 300s + Nombre de droplets ratés) | Les "Bananes" (fruits Spinners) ne sont pas pris en compte. |

Veuillez noter que si vous utilisez l'API pour calculer la précision, le nombre de droplets est sous **count50** et le nombre de droplets ratés est sous **countkatu**.

osu!mania
------------

Dans [osu!mania](/wiki/Game_Modes/osu!mania), la précision est calculée de manière similaire au mode [osu!](/wiki/Game_Modes/osu!).

**Précision = Total des points des notes / (Nombre de notes * 300)**

| Total des points des notes | Nombre de notes |
| -------------------------- | --------------- |
| (Nombre de droplets + Nombre de 100 + Nombre de 300) | (Nombre de Ratés + Nombre de 50 + Nombre de 100 + Nombre de 200 + Nombre de 300 + Nombre de MAX) |

Veuillez noter que MAX et 300 valent tout les deux le maximum dans le calcul de la précision, bien qu'un MAX soit plus fort qu'un 300 en terme de score.

Ecran de résultat
--------------------

### Classement (Ranking)

Votre rang (de D à SS) y est affiché, une vue d'ensemble de vos touches ainsi que la précision de la beatmap en pourcentage. Pour plus d'informations, regardez [Score](/wiki/Score).

![osu! Ranking Panel](Accuracy_osu!_Small.jpg "osu! Ranking Panel") ![osu!Taiko Ranking Panel](Accuracy_Taiko_Small.jpg "osu!Taiko Ranking Panel")

[osu! Ranking Panel (Agrandi)](Accuracy_osu!.jpg "Larger version of osu! Ranking Panel")

[osu!Taiko Ranking Panel (Agrandi)](Accuracy_Taiko.jpg "Larger version of osu!Taiko Ranking Panel")

![osu!CtB Ranking Panel (Agrandi)](Accuracy_CtB_Small.jpg "osu!CtB Ranking Panel") ![osu!Mania Ranking Panel](Accuracy_Mania_Small.jpg "osu!Mania Ranking Panel")

[osu!CtB Ranking Panel (Agrandi)](Accuracy_CtB.jpg "Larger version of Standard osu!CtB Panel")

[osu!Mania Ranking Panel (Agrandi)](Accuracy_Mania.jpg "Larger version of osu!Mania Ranking Panel")


### Graphique de Performance

Votre performance au cours de votre partie y est affichée. Des informations additionnelles sont affichées au survol du graphe :

![Performance Graph](Accuracy_TR.jpg "Performance Graph")

#### Accuracy
| Terme | Signification |
| ----- | ------------- |
| Error | **Ces deux valeurs représentent l'écart moyen en millisecondes des notes frappées trop tôt et trop tard.** Plus [l'OD](/wiki/Beatmap_Editor/Song_Setup) de la beatmap est haut, plus ces écarts devront être faible afin de bien réussir la beatmap. |
| Unstable Rate | **Cette valeur représente la consistance de vos frappes**. Plus cette valeur est faible plus vos frappes sont en rythme (les meilleurs joueurs ont en dessous de 100). Veuillez noter que cela mesure la consistance et non la précision, donc si vous tapez constamment 15ms en avance, vous aurez un résultat similaire dans le cas où vous tapez constamment sur le beat. La formule est essentiellement la déviation de la marge d'erreur multipliée par 10. |

#### Spin

Spin est affiché uniquement pour osu!

| Terme | Signification |
| ----- | ------------- |
| Speed | **Vitesse moyenne sur chaque spinner de la beatmap.** Max étant la vitesse maximale en RPM (Rounds Per Minute) sur l'un des spinners de la beatmap.
| Unstable Rate | **Valeur basée sur la variation moyenne de la vitesse de rotation**, plus la valeur est faible, mieux c'est. La formule est inconnue. |

**Notes**

-   Ces quatre valeurs ne sont pas sauvegardées et disparaîtront à la fermeture de osu!. Vous ne pouvez les revoir qu'en rejouant un replay sauvegardé.
-   Du fait de la façon dont les mods "Double Time" et "Half Time" sont implémentés, les valeurs "Error" et "Unstable Rate" seront multipliés par le facteur de vitesse de la beatmap. Afin d'obtenir les vraies valeurs en jouant DT, il faut diviser les résultats par 1.5. De même, il faut multiplier les résultats par 1.33 lorsque vous jouez en HT.

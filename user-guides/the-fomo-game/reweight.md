# Reweight

Reweights are used to return the Pancake spot price of the $KEY-$HERO pair back to 1. 

The algorithm is as follows: 

1. withdraw 99% of the $KEY and $HERO from pancake LP pool. 
2. execute a trade with held $KEY to bring the spot price back up to 1 
3. Mint needed $KEY so the LP pool will hold 1 million $KEY. 
4. deposit $KEY and $HERO so the LP pool has 1 million $KEY and 1 million HERO \(roughly\).
5. Burn the excessive $HERO.

{% hint style="info" %}
Only 99% is withdrawn because if there are no other LPs there could be rounding errors 
{% endhint %}




# Sal-s-Shipping-Company
Sal runs the biggest shipping company in the tri-county area, Sal’s Shippers. Sal wants to make sure that every single one of his customers has the best, and most affordable experience shipping their packages. In this project, I built a program that will take the weight of a package and determine the cheapest way to ship that package using Sal’s Shippers.  Sal’s Shippers has several different options for a customer to ship their package. They have ground shipping, which is a small flat charge plus a rate based on the weight of your package. Premium ground shipping, which is a much higher flat charge, but you aren’t charged for weight. They recently also implemented drone shipping, which has no flat charge, but the rate based on weight is triple the rate of ground shipping.
def price_function(weight,ppp,flat_charge):
  price = weight * ppp + flat_charge
  return price

def ground_shipping(weight):
  if weight <= 2:
    ppp,flat_charge = 1.5,20.00
    t = price_function(weight,ppp,flat_charge)
    return t
  elif not weight < 2 and weight <=6:
    ppp,flat_charge = 3.00, 20.00
    t = price_function(weight,ppp,flat_charge)
    return t
  elif weight > 6 and weight <= 10:
    ppp,flat_charge = 4.00,20.00
    t = price_function(weight,ppp,flat_charge)
    return t
  elif weight > 10:
    ppp,flat_charge = 4.75 , 20.00
    t = price_function(weight,ppp,flat_charge)
    return t

print(str("$") + str(ground_shipping(4.8)))

premium_ground_shipping = 125.00

def drone_shipping(weight):
  flat_charge = 0.00
  if weight <= 2:
    ppp = 4.50
    t = price_function(weight,ppp,flat_charge)
    return t
  elif weight > 2 and weight <= 6:
    ppp = 9.00
    t = price_function(weight,ppp,flat_charge)
    return t
  elif weight > 6 and weight <= 10:
    ppp = 12.00
    t = price_function(weight,ppp,flat_charge)
    return t 
  elif weight > 10:
    ppp = 14.25
    t = price_function(weight,ppp,flat_charge)
    return t
  
print(str("$") + str((drone_shipping(4.8))))

def cheapest_way(weight):
    m = ground_shipping(weight)  
    n = drone_shipping(weight)
    if m < n and m < premium_ground_shipping:
        print("Ground shipping is cheaper for this shipment.")
        return str("$") + str(ground_shipping(weight))
    elif n < m and n < premium_ground_shipping:
        print("Drone shipping is cheaper for this shipment.")
        return str("$") + str(drone_shipping(weight))
    else:
        print("Premium good shipping is cheaper")
        print(str("$125"))

print(cheapest_way(4.8))

print(cheapest_way(41.5))

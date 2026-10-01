import random
def handle_fun(db,sender,text,group_members):
    t=text.strip()
    if t=="تزويج":
        boys=[m for m in group_members if db["users"].get(m,{}).get("gender")=="ولد"]
        girls=[m for m in group_members if db["users"].get(m,{}).get("gender")=="بنت"]
        if not boys: boys=random.sample(group_members,1)
        if not girls: girls=random.sample(group_members,1)
        b=random.choice(boys); g=random.choice(girls)
        return f"💍 تم تزويج @{b} ❤️ @{g} (مزح)"
    if t=="خطف":
        a,b=random.sample(group_members,2)
        return f"🔫 @{a} خطف @{b} والفدية 2 مليون دولار 😂"
    return None

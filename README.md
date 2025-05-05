# Argument-Mining-with-AS-and-LLMs

## Examples (the context for the LLM)

1) *Analogy Based on Classification*:

   Argumentation scheme: [features(A1,A,B,C),features(A2,A,B,C),classified(A1,W)],classified(A2,W) 

    Example 1: The smartphone model QuantumFlow has the features: a high-resolution camera, an advanced processor, and a large storage capacity. The newer version, QuantumFlow Pro, has also the same features. The smartphone model QuantumFlow is properly classified as a flagship device. So, QuantumFlow Pro ought to be classified as a flagship device too.
   
    [features(smartphone_quantumFlow,high_resolution_camera,advanced_processor,large_storage_capacity),features(smartphone_quantumFlow_Pro,high_resolution_camera,advanced_processor,large_storage_capacity),classified(smartphone_quantumFlow,flagship_device)],classified(smartphone_quantumFlow_Pro,flagship_device)
   

3) *Effect to Cause*:

   Argumentation scheme: [occured(A),followed(occured(A),occurs(B))],occurs(B)

    Example 1: Generally, if a company provides excellent customer service, then customer satisfaction will increase. In this case, the company provides excellent customer service. Therefore, customer satisfaction will increase. 

    [occured(provides(company,excellent_customer_service),followed(occured(provides(company,excellent_customer_service)),increases(company,customer_satisfaction))],increases(company,customer_satisfaction)

5) *Need for Help*:
   
    Argumentation scheme: [would_help(A,X),can_carry_out(Y,A),not_too_costly(Y,A)],ought_to_carry_out(Y,A)

    Example 1: More books would help students. Teachers can hand out more books. It's not too costly for teachers to give out more books. Therefore, teachers ought to give out more books. 
  
    [would_help(more_books,students),can_carry_out(teachers,more_books),not_too_costly(teachers,more_books)],ought_to_carry_out(teachers,more_books)


7) *Argument from Opposities*:

     Argumentation scheme: [has_property(R,P),is_opposite(R,S)],has_property(S,opposite_of(P))

     Example 1: Fire has the property of hot. Fire is the opposite of ice. Therefore, ice has the opposite of hot as a property.

     [has_property(fire,hot),is_opposite(fire,ice)],has_property(ice,opposite_of(hot))

9) *Moral Justification Ad Populum Argument*:

    Argumentation scheme: [everybody_who_is(Y,accept(P)),goal_of(X,Y)],should(X,accept(P))

    Example 1: Everybody who is compassionate accepts forgiveness. John's goal is to be compassionate. Therefore, John should accept forgiveness.

     [everybody_who_is(compassionate,accept(forgiveness)),goal_of(john,compassionate)],should(john,accept(forgiveness))

11) *Classification*:

     Argumentation scheme: [classification(F,G),be(A,F)],be(A,G)

     Example 1: All eagles are birds. White eagles are eagles. Therefore, white eagles are birds.

     [classification(eagle,bird),be(white_eagle,eagle)],be(white_eagle,bird)

13) *Necessary Condition*:

     Argumentation scheme: [goal(Sn),necessary_condition(Sn,Si)],is_necessary(Si)

     Example 1: Pursuing advancements in renewable energy technology is my objective. In order to realize this, investing in solar power infrastructure is necessary. Therefore, I need to invest in solar power infrastructure.
   
     [goal(pursue(advancements,renewable_energy_techonology)),necessary_condition(pursue(advancements,renewable_energy_techonology),invest(solar_power_infrastructure))],is_necessary(invest(solar_power_infrastructure))

15) *Position to Know*:

     Argumentation scheme: [position_to_know(A,S),asserts(A,Ar),contain(S,Ar)],Ar.

     Example 1: Daniel is a meteorologist and claims that low pressure systems often bring stormy weather, so we can deduce that low pressure systems often bring stormy weather.

     [position_to_know("Daniel",meteorology),asserts("Daniel",brings(low_pressure_systems,stormy_weather)),contain(meteorology,brings(low_pressure_systems,stormy_weather))],brings(low_pressure_systems,stormy_weather)






## "Argument from Position to Know" tests

1) **Natural Language Text**: E-Books: A Game-Changer for Learning? Dr. Samuel Harper's Perspective. Dr. Samuel Harper, a seasoned educational psychologist with over two decades of experience, is in a position to know about the effects of e-books on learning outcomes. Drawing on his extensive research in the field of educational technology, Dr. Harper asserts, "E-books can enhance comprehension and engagement." Based on his expertise and assertion, the conclusion follows: E-books can enhance comprehension and engagement.
   
    **Computational Representation of the Argument**: [position_to_know("Dr. Samuel Harper",educational_technology),asserts("Dr. Samuel Harper",enhance(e_books,comprehension_and_engagement)),contain(educational_technology,enhance(e_books,comprehension_and_engagement))],enhance(e_books,comprehension_and_engagement)

2) **Natural Language Text**: The Hidden Dangers of Lead: Dr. Alan Porter's Groundbreaking Research. In the 1960s, leaded gasoline was a staple of the automotive industry, and few questioned its safety. But Dr. Alan Porter, a chemist born in 1935, grew concerned about lead's impact on human health. In his 1974 study, he found that lead exposure was linked to developmental issues in children. Dr. Porter stated, “Lead in gasoline is poisoning our children.” His findings were a wake-up call, leading to the gradual phasing out of leaded fuel and a major shift in public health policies worldwide.

     **Computational Representation of the Argument**: [position_to_know("Dr. Alan Porter",chemistry),asserts("Dr. Alan Porter",poisoning(lead_in_gasoline,children)),contain(chemistry,poisoning(lead_in_gasoline,children))],poisoning(lead_in_gasoline,children)

3) **Natural Language Text**: The Truth about Asbestos: Dr. Evelyn Chang's Revelations. Asbestos was widely used in construction throughout the 20th century, valued for its fire-resistant properties. However, Dr. Evelyn Chang, an epidemiologist born in 1929, discovered its deadly consequences. In 1968, she found that prolonged exposure to asbestos fibers caused lung cancer and mesothelioma. Dr. Chang declared, "Asbestos exposure is a serious health hazard". Her statement played a key role in stricter regulations and the eventual banning of asbestos in many countries.	

    **Computational Representation of the Argument**: [position_to_know("Dr. Evelyn Chang",epidemiology),asserts("Dr. Evelyn Chang",is_serious_health_hazard(asbestos_exposure)),contain(epidemiology,is_serious_health_hazard(asbestos_exposure))],is_serious_health_hazard(asbestos_exposure)

4) **Natural Language Text**: The Real Cause of Peptic Ulcers: Dr. Paul Harrison's Surprising Discovery. For years, peptic ulcers were thought to be caused by stress and spicy foods. But in 1982, Dr. Paul Harrison, a gastroenterologist born in 1942, challenged this belief. His research showed that a bacterium, Helicobacter pylori, was the actual cause of most ulcers. Dr. Harrison said, "Bacteria, not stress, cause peptic ulcers." This revelation revolutionized ulcer treatment, as antibiotics became the standard care instead of antacids and lifestyle changes.	

    **Computational Representation of the Argument**: [position_to_know("Dr. Paul Harrison",gastroenterology),asserts("Dr. Paul Harrison",cause(helicobacter_pylori,peptic_ulcers)),contain(gastroenterology,cause(helicobacter_pylori,peptic_ulcers))],cause(helicobacter_pylori,peptic_ulcers)

5) **Natural Language Text**: The Consequences of Plastic: Dr. Linda Walsh's Environmental Warning. In the 1980s, plastic was seen as a convenient and durable material. But Dr. Linda Walsh, an environmental scientist born in 1951, discovered the environmental impact of microplastics on marine life. Her research in 1990 showed that plastic particles were harming aquatic ecosystems. Dr. Walsh warned, "Microplastics are polluting our oceans." This statement raised public awareness about plastic waste and spurred initiatives to reduce plastic use and improve recycling efforts globally.	

    **Computational Representation of the Argument**: [position_to_know("Dr. Linda Walsh",environmental_science),asserts("Dr. Linda Walsh",pollute(microplastics,oceans)),contain(environmental_science,pollute(microplastics,oceans))],pollute(microplastics,oceans)

6) **Natural Language Text**: The Heart Risks of Trans Fats: Dr. Michael Sims' Health Alert. Trans fats were once common in processed foods and seen as a safe alternative to saturated fats. However, Dr. Michael Sims, a nutritionist born in 1948, found that trans fats significantly increased the risk of heart disease. In 1995, he published his findings, linking trans fats to cardiovascular issues. Dr. Sims stated, "Trans fats are harmful to heart health." His research led to widespread reformulation of food products and the eventual banning of trans fats in several countries.	

    **Computational Representation of the Argument**: [position_to_know("Dr. Michael Sims",nutrition),asserts("Dr. Michael Sims",harmful(trans_fats,heart_health)),contain(nutrition,harmful(trans_fats,heart_health))],harmful(trans_fats,heart_health)
    
7) **Natural Language Text**: The Role of Vitamin D: Dr. Sarah Thompson’s Groundbreaking Findings: In the early 2000s, many believed that vitamin D was simply important for bone health. However, Dr. Sarah Thompson, an endocrinologist born in 1972, sought to understand its broader implications. Her research revealed that vitamin D deficiency was linked to various chronic diseases, including diabetes and autoimmune disorders. Dr. Thompson stated, “Vitamin D is crucial for overall health, not just bones.” Her findings prompted a reevaluation of dietary guidelines and increased awareness of vitamin D's importance in maintaining general health.	

    **Computational Representation of the Argument**: [position_to_know("Dr. Sarah Thompson",endocrinology),asserts("Dr. Sarah Thompson",crucial(vitamin_d,overall_health)),contain(endocrinology,crucial(vitamin_d,overall_health))],crucial(vitamin_d,overall_health)

8) **Natural Language Text**: The Link Between Sleep and Mental Health: Dr. James Carter’s Discovery: For years, the relationship between sleep and mental health was not fully understood. Dr. James Carter, a psychologist born in 1968, conducted studies in the late 1990s that demonstrated how sleep deprivation could exacerbate anxiety and depression. Dr. Carter stated, “Poor sleep increases the risk of mental health issues.” This revelation led to greater emphasis on sleep hygiene in mental health treatment and awareness campaigns about the importance of sleep for mental well-being.

    **Computational Representation of the Argument**: [position_to_know("Dr. James Carter",psychology),asserts("Dr. James Carter",increases(poor_sleep,mental_health_issues)),contain(psychology,increases(poor_sleep,mental_health_issues))],increases(poor_sleep,mental_health_issues)
    
9) **Natural Language Text**: The Connection Between Gut Health and Mood: Dr. Emma Rivera’s Insight: In the 2010s, many viewed gut health as unrelated to mental well-being. However, Dr. Emma Rivera, a microbiologist born in 1980, conducted research that indicated a strong connection between gut bacteria and mood regulation. Dr. Rivera stated, “A healthy gut can improve mental health.” Her work encouraged dietary changes that promote gut health, leading to increased interest in the gut-brain axis.	

    **Computational Representation of the Argument**: [position_to_know("Dr. Emma Rivera",microbiology),asserts("Dr. Emma Rivera",improve(healthy_gut,mental_health)),contain(microbiology,improve(healthy_gut,mental_health))],improve(healthy_gut,mental_health)
    
10) **Natural Language Text**: The Effects of Air Pollution on Children’s Health: Dr. Marco Lee’s Research: For decades, air pollution was primarily viewed as an environmental issue. Dr. Marco Lee, an environmental health scientist born in 1975, found in his 2015 study that children exposed to high levels of air pollution had a higher risk of developing asthma and other respiratory issues. Dr. Lee stated, “Air pollution is harming our children’s health.” His findings fueled advocacy for cleaner air regulations and public health initiatives focused on reducing pollution exposure.	

    **Computational Representation of the Argument**: [position_to_know("Dr. Marco Lee",environmental_health),asserts("Dr. Marco Lee",harms(air_pollution,childrens_health)),contain(environmental_health,harms(air_pollution,childrens_health))],harms(air_pollution,childrens_health)
    
11) **Natural Language Text**: The Impact of Screen Time on Child Development: Dr. Rachel Foster’s Findings: In the late 2010s, many parents viewed screen time as a harmless pastime for children. However, Dr. Rachel Foster, a child psychologist born in 1985, discovered that excessive screen time could lead to developmental delays in language and social skills. Dr. Foster stated, “Too much screen time negatively affects children’s development.” Her research sparked discussions about screen time limits and the importance of balanced activities for healthy child development.	  

    **Computational Representation of the Argument**: [position_to_know("Dr. Rachel Foster",child_psychology),asserts("Dr. Rachel Foster",negatively_affects(excessive_screen_time,childrens_development)),contain(child_psychology,negatively_affects(excessive_screen_time,children s_development))],negatively_affects(excessive_screen_time,children s_development)

12) **Natural Language Text**: The Evolution of Public Health Awareness: John’s Pioneering Insights on Smoking. John was born in New Zealand in 1928 and grew up in a world where smoking was not only a common habit but also a cultural phenomenon. By the time he graduated in Medicine in 1953, he had witnessed the growing popularity of cigarettes, which were often glamorized in advertisements and associated with sophistication. The societal perception of smoking was so deeply ingrained that it was seen as a status symbol, particularly among the elite. However, the landscape of public health was about to change. In 1970, John participated in an interview that would prove to be pivotal in the fight against tobacco use. During this interview, he expressed his concerns about the health risks associated with smoking. He stated that smoking causes cancer due to the chemical substances present in cigarettes. This assertion was groundbreaking; until that moment, the link between smoking and severe health issues was not widely acknowledged. John's revelation sparked significant discourse in the medical community and among the general public. It highlighted the urgent need for more research into the health effects of smoking and challenged the perception that smoking was merely a harmless indulgence. As people began to understand the dangers of tobacco, public health campaigns started to emerge, aimed at educating the public about the risks associated with smoking. His statement was particularly impactful because it came at a time when the tobacco industry was powerful, and many smokers were reluctant to accept that their habit could be detrimental to their health. John’s insights helped to shift the narrative surrounding smoking from one of glamour and status to one of caution and concern. In the years that followed, a growing body of research began to confirm John’s assertions. Studies linked smoking not only to lung cancer but also to various other forms of cancer, heart disease, and respiratory illnesses. The medical community rallied around this evidence, and public health initiatives aimed at reducing smoking rates began to take shape. John's contribution to this important conversation was not just a personal achievement; it represented a larger movement toward understanding the health implications of lifestyle choices. Today, we recognize the immense value of his early advocacy for smoking awareness. His willingness to speak out against the status quo helped to lay the groundwork for future generations of researchers, doctors, and public health advocates who continue to fight against tobacco use and promote healthier lifestyles.

    **Computational Representation of the Argument**: [position_to_know("John",medicine),asserts("John",causes(smoking,cancer)),contain(medicine,causes(smoking,cancer))],causes(smoking,cancer)

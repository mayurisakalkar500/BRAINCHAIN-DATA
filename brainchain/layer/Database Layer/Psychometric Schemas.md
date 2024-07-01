[[All Types Of Psychometric Questions]]
[[Selected For Psychometric Questions]]
[[Schema for all type of Questions]]


CREATE TABLE PersonalDichotomyTraits(
    user_id INT PRIMARY KEY AUTO_INCREMENT,
    introversion_extraversion INT CHECK (introversion_extraversion >= 0 AND introversion_extraversion <= 100),
    thinking_feeling INT CHECK (thinking_feeling >= 0 AND thinking_feeling <= 100),
    judging_perceiving INT CHECK (judging_perceiving >= 0 AND judging_perceiving <= 100),
    sensing_intuition INT CHECK (sensing_intuition >= 0 AND sensing_intuition <= 100),
    openness_conventionality INT CHECK (openness_conventionality >= 0 AND openness_conventionality <= 100),
    agreeableness_antagonism INT CHECK (agreeableness_antagonism >= 0 AND agreeableness_antagonism <= 100),
    conscientiousness_lack_of_direction INT CHECK (conscientiousness_lack_of_direction >= 0 AND conscientiousness_lack_of_direction <= 100),
    neuroticism_emotional_stability INT CHECK (neuroticism_emotional_stability >= 0 AND neuroticism_emotional_stability <= 100),
    assertiveness_passiveness INT CHECK (assertiveness_passiveness >= 0 AND assertiveness_passiveness <= 100),
    independence_conformity INT CHECK (independence_conformity >= 0 AND independence_conformity <= 100),
    optimism_pessimism INT CHECK (optimism_pessimism >= 0 AND optimism_pessimism <= 100),
    leadership_followership INT CHECK (leadership_followership >= 0 AND leadership_followership <= 100),
    practicality_imagination INT CHECK (practicality_imagination >= 0 AND practicality_imagination <= 100),
    realism_idealism INT CHECK (realism_idealism >= 0 AND realism_idealism <= 100),
    activity_passivity INT CHECK (activity_passivity >= 0 AND activity_passivity <= 100),
    altruism_self_interest INT CHECK (altruism_self_interest >= 0 AND altruism_self_interest <= 100),
    flexibility_rigidity INT CHECK (flexibility_rigidity >= 0 AND flexibility_rigidity <= 100),
    adaptability_stability INT CHECK (adaptability_stability >= 0 AND adaptability_stability <= 100),
    risk_taking_caution INT CHECK (risk_taking_caution >= 0 AND risk_taking_caution <= 100),
    ambition_contentment INT CHECK (ambition_contentment >= 0 AND ambition_contentment <= 100),
    sociability_solitude INT CHECK (sociability_solitude >= 0 AND sociability_solitude <= 100),
    empathy_apathy INT CHECK (empathy_apathy >= 0 AND empathy_apathy <= 100),
    confidence_insecurity INT CHECK (confidence_insecurity >= 0 AND confidence_insecurity <= 100),
    enthusiasm_indifference INT CHECK (enthusiasm_indifference >= 0 AND enthusiasm_indifference <= 100),
    patience_impatience INT CHECK (patience_impatience >= 0 AND patience_impatience <= 100),
    humility_arrogance INT CHECK (humility_arrogance >= 0 AND humility_arrogance <= 100),
    forgiveness_resentment INT CHECK (forgiveness_resentment >= 0 AND forgiveness_resentment <= 100),
    trust_suspicion INT CHECK (trust_suspicion >= 0 AND trust_suspicion <= 100),
    creativity_predictability INT CHECK (creativity_predictability >= 0 AND creativity_predictability <= 100),
    competitiveness_cooperation INT CHECK (competitiveness_cooperation >= 0 AND competitiveness_cooperation <= 100)
);

INSERT INTO PersonalDichotomyTraits(
    introversion_extraversion, thinking_feeling, judging_perceiving, sensing_intuition, openness_conventionality,
    agreeableness_antagonism, conscientiousness_lack_of_direction, neuroticism_emotional_stability,
    assertiveness_passiveness, independence_conformity, optimism_pessimism, leadership_followership,
    practicality_imagination, realism_idealism, activity_passivity, altruism_self_interest, flexibility_rigidity,
    adaptability_stability, risk_taking_caution, ambition_contentment, sociability_solitude, empathy_apathy,
    confidence_insecurity, enthusiasm_indifference, patience_impatience, humility_arrogance, forgiveness_resentment,
    trust_suspicion, creativity_predictability, competitiveness_cooperation
) VALUES (
    75, 40, 65, 50, 80, 60, 70, 55, 45, 85, 75, 90, 65, 50, 70, 80, 55, 60, 50, 85, 75, 70, 80, 65, 60, 70, 75, 55, 80, 60
);

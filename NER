package ner;

import edu.stanford.nlp.pipeline.*;
import java.util.*;

public class NERTagger {
    public static void main(String[] args) {
       
        Properties props = new Properties();
        props.setProperty("annotators", "tokenize,ssplit,pos,lemma,ner");
        StanfordCoreNLP pipeline = new StanfordCoreNLP(props);

        
        String text = "Barack Obama was born in Hawaii and served as the president of the United States.";

       
        Annotation document = new Annotation(text);
        pipeline.annotate(document);

        System.out.println("Named Entities in the text:\n");
        for (CoreMap sentence : document.get(CoreAnnotations.SentencesAnnotation.class)) {
            for (CoreLabel token : sentence.get(CoreAnnotations.TokensAnnotation.class)) {
                String word = token.word();
                String ner = token.get(CoreAnnotations.NamedEntityTagAnnotation.class);

                if (!"O".equals(ner)) {
                    System.out.println(word + " : " + ner);
                }
            }
        }
    }
}


[#Laboratory Work 3 Activity Colab](https://colab.research.google.com/drive/1PO6qKMWidP6CUo5DVqxbL0wDe0F5wZFJ?usp=drive_link).


#GUIDE QUESTIONS (Student Explanation & Reflection)
A. Model Evaluation Analysis
1. What were the weakest-performing classes based on the confusion matrix?
    >The weakest-performing class is anthurium. You can see it has the lowest number on the diagonal (21), and it is frequently confused with many other classes (like dendrodium and lerio). Another weak class is catleya (28), which is often misclassified as dancinglady.
    
2. How did Precision, Recall, and F1-score vary across classes?
    > High Performance: Classes like dancinglady (49), euphorbia (48), and tigerorchid (46) have very high scores. The model is very good at identifying these distinct flower types.
    Low Performance: The "orchids" (like anthurium, catleya, and phalaenopsis) likely have lower scores because they share similar shapes or colors, making it harder for the CNN to tell them apart.
    
3. What does a low recall indicate in your model?
    >For the anthurium class, a low recall means that when the model is shown an actual anthurium, it often fails to recognize it. Instead, it "guesses" that it is a dendrodium (6 times) or lerio (7 times). The model is "missing" nearly half of the anthurium images in your test set.
    
4. How does AUC score reflect model performance compared to accuracy?
    > While overall accuracy looks decent because many classes have high numbers (40+), the AUC score would be slightly lower for the "orchids" group. Accuracy just counts the correct 21 hits for anthurium, but AUC tells us how "confused" the model was—in this case, quite confused, as the predictions are scattered across almost 10 different wrong categories.

B. Model Improvement

5. How did data augmentation affect validation accuracy?
    >It helps the model see flowers from different angles. This prevents the model from just memorizing one photo, usually leading to higher validation accuracy.
    
6. Why is Batch Normalization important in CNNs?
    >It makes training faster and more stable by re-scaling the data between layers. It helps the model learn more efficiently.
    
7. What role did Dropout play in improving your model?
    >Dropout randomly "turns off" parts of the model during training. This forces the model to learn better features and stops it from overfitting (memorizing).

8. How did Early Stopping prevent overfitting?
    >It stops the training automatically when the Validation Loss stops getting better. This ensures you keep the "best" version of the model before it starts memorizing noise.

C. Performance Comparison
9. What improvements were observed after modifying the model?
10. Which enhancement contributed the most to performance improvement? Why?
11. Did the gap between training and validation accuracy decrease? Explain.
D. Explainability (Grad-CAM Integration)
12. How did Grad-CAM help in understanding model predictions?
    >If you ran Grad-CAM on firecracker, you might see the heatmap lighting up on the specific long, tubular petals. Since the model confused firecracker with calendula 12 times, Grad-CAM would help you see if the model is mistakenly looking at the leaf color or the background instead of the flower itself.
    
13. Did the improved model focus on more relevant regions? Provide evidence.
    >In an improved model, we want the heatmap to be tightly centered on the flower. If your baseline model had a "scattered" heatmap (showing it was guessing based on noise), but the improved model shows a "focused" heatmap on the flower's center, that is visual evidence that Batch Normalization and Data Augmentation helped the model learn specific shapes rather than just colors.
    
14. Why is explainability important in real-world AI applications?
    

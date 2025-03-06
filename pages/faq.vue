<template>
  <UButton
    to="/"
    icon="i-heroicons-arrow-left"
    size="sm"
    color="gray"
    variant="outline"
    class="mb-4"
    >Retour à l'accueil
  </UButton>

  <UAccordion
    multiple
    :items="[
      {
        label: 'Où ces prix sont-ils obtenus ?',
        content:
          'Nous utilisons l\'API Product Advertising d\'Amazon pour récupérer les informations sur les produits.',
      },
      {
        label: 'À quelle fréquence ce site est-il mis à jour ?',
        content: 'Les prix sont mis à jour toutes les quatre heures.',
      },
      {
        label: 'Qu\'en est-il de l\'expédition ?',
        content:
          'Les prix indiqués ici n\'incluent pas les frais d\'expédition et les taxes, car nous ne savons pas où vous vivez. La majorité de ces annonces incluent la livraison gratuite, surtout si vous avez Amazon Prime, mais assurez-vous de vérifier les coûts d\'expédition avant de passer une commande.',
      },
      {
        label: 'Est-ce une publicité ?',
        content:
          'Nous recevons des commissions pour les produits achetés via les liens sur ce site par le biais du programme d\'affiliation d\'Amazon.',
      },
      {
        label: 'Informations supplémentaires',
        content:
          'Envoyez un e-mail à support@scanprice.com pour toute question supplémentaire.',
      },
    ]"
  />
</template>

<script setup lang="ts">
definePageMeta({
  layout: "default",
});
</script>

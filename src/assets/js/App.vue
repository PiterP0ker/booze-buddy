<template>
	<section class="ba-section-cards">
	<div class="row align-center">
		<div class="column large-10 small-12">
			<div class="ba-search-filters">
				<button class="button" type="button" data-toggle="example-dropdown-bottom-center">
					<div class="ba-fillters-button">
						<svg width="20" height="20">
							<use xlink:href="#icon-search" />
						</svg>
						<span class="ba-button-text">Уточнить детали поиска</span>
					</div>
				</button>
				<div class="dropdown-pane" data-position="bottom" data-alignment="center"
					id="example-dropdown-bottom-center" data-dropdown data-auto-focus="true">

				</div>
			</div>
			<!-- /.ba-search-filters -->
				<div class="person-card person-card-first" v-for="card in cards">
			<a href="#" id="search">
					<div class="row">
						<div class="column large-3">
							<img :src="card.img" :alt="card.name">
						</div>
						<!-- /.column -->
						<div class="column">
							<div class="ba-person-name">{{card.name}}</div>
							<div class="ba-card-info">
								<span class="ba-rating">&#9733 &#9733 &#9733 &#9733</span>
								<span class="ba-data">{{card.date}}</span>
							</div>
							<div class="row">
								<div class="column">
									<div class="ba-person-list-info">
										<ul class="ba-list--2col">
											<li>
												<span class="ba-value">Город:</span>
												<span class="ba-answer">{{card.city}}</span>
											</li>
											<li>
												<span class="ba-value">Повод:</span>
												<span class="ba-answer">{{card.reason}}</span>
											</li>
											<li>
												<span class="ba-value">Компания:</span>
												<span class="ba-answer">{{card.company}}</span>
											</li>
											<li>
												<span class="ba-value">Заведение:</span>
												<span class="ba-answer">{{card.place}}</span>
											</li>
											<li>
												<span class="ba-value">Напиток:</span>
												<span class="ba-answer">{{card.drink}}</span>
											</li>
										</ul>
									</div>
									<!-- /.ba-person-list-info -->
								</div>
							</div>
						</div>
						<!-- /.column -->

						<div class="ba-like">
							<svg width="21" height="20" viewBox="0 0 21 20" fill="none" xmlns="http://www.w3.org/2000/svg">
								<path
									d="M10.4999 19.2396L8.9895 17.8646C3.62492 13 0.083252 9.79167 0.083252 5.85417C0.083252 2.64583 2.60409 0.125 5.81242 0.125C7.62492 0.125 9.3645 0.96875 10.4999 2.30208C11.6353 0.96875 13.3749 0.125 15.1874 0.125C18.3958 0.125 20.9166 2.64583 20.9166 5.85417C20.9166 9.79167 17.3749 13 12.0103 17.875L10.4999 19.2396Z"
									fill="#D7B7FD" />
							</svg>
						</div>
					</div>
			</a>
				</div>
				<!-- /.person-card -->
		</div>
	</div>
</section>
<!-- /.ba-section-cards -->
</template>

<script>
	// import json from './json/cards.json';
export default {
	data() {
		return {
			cards: []
		}
	},
	mounted(){
		fetch('assets/json/cards.json')
		.then(res => res.json())
		.then(list => {
			this.cards = list
		console.log(this.cards);
			})
		
	}
};
</script>